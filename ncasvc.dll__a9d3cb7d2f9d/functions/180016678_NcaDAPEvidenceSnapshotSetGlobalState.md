# NcaDAPEvidenceSnapshotSetGlobalState

- ea: `0x180016678`
- end: `0x180016791`
- name: `NcaDAPEvidenceSnapshotSetGlobalState`
- size: `281`
- prototype: `void __fastcall(int, int)`
- caller_count: `18`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180006190`
- `0x180006940`
- `0x18000ff30`
- `0x180010350`
- `0x180010710`
- `0x180010aa0`
- `0x180011744`
- `0x180013b40`
- `0x180013f60`
- `0x180014620`
- `0x1800147d0`
- `0x180014b80`
- `0x180014e00`
- `0x180015430`
- `0x1800154f0`
- `0x1800155e0`
- `0x1800164e0`

## callees

- `0x1800163cc`
- `0x180016678`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001673c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001676a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001673c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001676a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016753`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016753`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001671d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001671d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800166a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800166a6`

## pseudocode

```c
void __fastcall NcaDAPEvidenceSnapshotSetGlobalState(int a1, int a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // r9d
  _SYSTEMTIME v7; // xmm0
  struct NCA_DAP_USER_EVSNPSHT_ *i; // rdi
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-58h] BYREF

  v2 = a1;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  EnterCriticalSection(&gNcaDapEvSnpshot);
  v6 = *((_DWORD *)&gNcaDapEvSnpshot + 5 * v2 + 12);
  if ( v6 != a2 )
  {
    if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
      McTemplateU0qttx_EventWriteTransfer(v5, v4, (unsigned int)v2, v6, a2, 0);
    v7 = SystemTime;
    *((_DWORD *)&gNcaDapEvSnpshot + 5 * v2 + 12) = a2;
    *(_SYSTEMTIME *)((char *)&gNcaDapEvSnpshot + 20 * v2 + 52) = v7;
    for ( i = qword_180029528;
          i != (struct NCA_DAP_USER_EVSNPSHT_ *)&qword_180029528;
          i = *(struct NCA_DAP_USER_EVSNPSHT_ **)i )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)i + 64));
      *((_DWORD *)i + 5 * v2 + 28) = a2;
      *(_SYSTEMTIME *)((char *)i + 20 * v2 + 116) = SystemTime;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)i + 64));
      SetEvent(*(HANDLE *)(*((_QWORD *)i + 78) + 8LL));
    }
  }
  LeaveCriticalSection(&gNcaDapEvSnpshot);
}

```

## disassembly

```asm
0x180016678  push    rbx
0x18001667a  push    rbp
0x18001667b  push    rsi
0x18001667c  push    rdi
0x18001667d  push    r14
0x18001667f  push    r15
0x180016681  sub     rsp, 58h
0x180016685  mov     rax, cs:__security_cookie
0x18001668c  xor     rax, rsp
0x18001668f  mov     [rsp+88h+var_48], rax
0x180016694  movsxd  rbx, ecx
0x180016697  xorps   xmm0, xmm0
0x18001669a  lea     rcx, [rsp+88h+SystemTime]; lpSystemTime
0x18001669f  mov     ebp, edx
0x1800166a1  movups  xmmword ptr [rsp+88h+SystemTime.wYear], xmm0
0x1800166a6  call    cs:__imp_GetSystemTime
0x1800166ad  nop     dword ptr [rax+rax+00h]
0x1800166b2  lea     r14, ?gNcaDapEvSnpshot@@3UNCA_DAP_EVSNPSHT_COMPONENT_@@A; NCA_DAP_EVSNPSHT_COMPONENT_ gNcaDapEvSnpshot
0x1800166b9  mov     rcx, r14; lpCriticalSection
0x1800166bc  call    cs:__imp_EnterCriticalSection
0x1800166c3  nop     dword ptr [rax+rax+00h]
0x1800166c8  lea     rsi, [rbx+rbx*4]
0x1800166cc  mov     r9d, [r14+rsi*4+30h]
0x1800166d1  cmp     r9d, ebp
0x1800166d4  jz      loc_180016767
0x1800166da  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x1800166e1  jz      short loc_1800166F8
0x1800166e3  mov     [rsp+88h+var_60], 0
0x1800166ec  mov     r8d, ebx
0x1800166ef  mov     [rsp+88h+var_68], ebp
0x1800166f3  call    McTemplateU0qttx_EventWriteTransfer
0x1800166f8  movups  xmm0, xmmword ptr [rsp+88h+SystemTime.wYear]
0x1800166fd  mov     [r14+rsi*4+30h], ebp
0x180016702  lea     r15, qword_180029528
0x180016709  movdqu  xmmword ptr [r14+rsi*4+34h], xmm0
0x180016710  mov     rdi, cs:qword_180029528
0x180016717  jmp     short loc_180016762
0x180016719  lea     rcx, [rdi+40h]; lpCriticalSection
0x18001671d  call    cs:__imp_EnterCriticalSection
0x180016724  nop     dword ptr [rax+rax+00h]
0x180016729  mov     [rdi+rsi*4+70h], ebp
0x18001672d  lea     rcx, [rdi+40h]; lpCriticalSection
0x180016731  movups  xmm0, xmmword ptr [rsp+88h+SystemTime.wYear]
0x180016736  movdqu  xmmword ptr [rdi+rsi*4+74h], xmm0
0x18001673c  call    cs:__imp_LeaveCriticalSection
0x180016743  nop     dword ptr [rax+rax+00h]
0x180016748  mov     rcx, [rdi+270h]
0x18001674f  mov     rcx, [rcx+8]; hEvent
0x180016753  call    cs:__imp_SetEvent
0x18001675a  nop     dword ptr [rax+rax+00h]
0x18001675f  mov     rdi, [rdi]
0x180016762  cmp     rdi, r15
0x180016765  jnz     short loc_180016719
0x180016767  mov     rcx, r14; lpCriticalSection
0x18001676a  call    cs:__imp_LeaveCriticalSection
0x180016771  nop     dword ptr [rax+rax+00h]
0x180016776  mov     rcx, [rsp+88h+var_48]
0x18001677b  xor     rcx, rsp; StackCookie
0x18001677e  call    __security_check_cookie
0x180016783  add     rsp, 58h
0x180016787  pop     r15
0x180016789  pop     r14
0x18001678b  pop     rdi
0x18001678c  pop     rsi
0x18001678d  pop     rbp
0x18001678e  pop     rbx
0x18001678f  retn
```
