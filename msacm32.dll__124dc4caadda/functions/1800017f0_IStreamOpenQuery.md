# IStreamOpenQuery

- ea: `0x1800017f0`
- end: `0x1800018cc`
- name: `IStreamOpenQuery`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e70`

## callees

- `0x1800017f0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800018af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001843`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001843`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000189c`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000189c`

## pseudocode

```c
__int64 __fastcall IStreamOpenQuery(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 (__fastcall *v7)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD); // rax
  unsigned int v8; // edi
  HDRVR v9; // rcx
  _DWORD lParam1[3]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+3Ch] [rbp-4Ch]
  __int64 v13; // [rsp+44h] [rbp-44h]
  __int64 v14; // [rsp+4Ch] [rbp-3Ch]
  __int64 v15; // [rsp+54h] [rbp-34h]
  int v16; // [rsp+5Ch] [rbp-2Ch]
  __int128 v17; // [rsp+60h] [rbp-28h]
  int v18; // [rsp+70h] [rbp-18h]

  lParam1[0] = 68;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 - 5);
  *(_QWORD *)&lParam1[1] = a2;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v12 = a3;
  v13 = a4;
  v16 = a5 | 1;
  EnterCriticalSection((LPCRITICAL_SECTION)a1 - 1);
  if ( !a1 )
    goto LABEL_8;
  v7 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD))a1[6];
  if ( !v7 )
  {
    v9 = (HDRVR)a1[5];
    if ( v9 )
    {
      v8 = SendDriverMessage(v9, 0x604Cu, (LPARAM)lParam1, 0);
      goto LABEL_9;
    }
LABEL_8:
    v8 = 5;
    goto LABEL_9;
  }
  if ( v7 == (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD))-1LL )
    v8 = 1;
  else
    v8 = v7(a1[7], *(_QWORD *)((char *)a1 + 20), 24652, lParam1, 0);
LABEL_9:
  LeaveCriticalSection(v5);
  return v8;
}

```

## disassembly

```asm
0x1800017f0  mov     rax, rsp
0x1800017f3  mov     [rax+8], rbx
0x1800017f7  mov     [rax+10h], rsi
0x1800017fb  push    rdi
0x1800017fc  sub     rsp, 80h
0x180001803  mov     dword ptr [rax-58h], 44h ; 'D'
0x18000180a  lea     rbx, [rcx-28h]
0x18000180e  mov     [rax-54h], rdx
0x180001812  xor     esi, esi
0x180001814  mov     [rax-3Ch], rsi
0x180001818  xorps   xmm0, xmm0
0x18000181b  mov     [rax-34h], rsi
0x18000181f  mov     rdi, rcx
0x180001822  movdqa  xmmword ptr [rax-28h], xmm0
0x180001827  mov     rcx, rbx; lpCriticalSection
0x18000182a  mov     [rax-18h], esi
0x18000182d  mov     [rax-4Ch], r8
0x180001831  mov     [rax-44h], r9
0x180001835  mov     eax, [rsp+88h+arg_20]
0x18000183c  or      eax, 1
0x18000183f  mov     [rsp+88h+var_2C], eax
0x180001843  call    cs:__imp_EnterCriticalSection
0x180001849  test    rdi, rdi
0x18000184c  jz      short loc_1800018A7
0x18000184e  mov     rax, [rdi+30h]
0x180001852  test    rax, rax
0x180001855  jz      short loc_180001886
0x180001857  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000185b  jnz     short loc_180001864
0x18000185d  mov     edi, 1
0x180001862  jmp     short loc_1800018AC
0x180001864  mov     rdx, [rdi+14h]
0x180001868  lea     r9, [rsp+88h+lParam1]
0x18000186d  mov     rcx, [rdi+38h]
0x180001871  mov     r8d, 604Ch
0x180001877  mov     [rsp+88h+var_68], rsi
0x18000187c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001881  mov     rdi, rax
0x180001884  jmp     short loc_1800018AC
0x180001886  mov     rcx, [rdi+28h]; hDriver
0x18000188a  test    rcx, rcx
0x18000188d  jz      short loc_1800018A7
0x18000188f  xor     r9d, r9d; lParam2
0x180001892  lea     r8, [rsp+88h+lParam1]; lParam1
0x180001897  mov     edx, 604Ch; message
0x18000189c  call    cs:__imp_SendDriverMessage
0x1800018a2  mov     rdi, rax
0x1800018a5  jmp     short loc_1800018AC
0x1800018a7  mov     edi, 5
0x1800018ac  mov     rcx, rbx; lpCriticalSection
0x1800018af  call    cs:__imp_LeaveCriticalSection
0x1800018b5  lea     r11, [rsp+88h+var_8]
0x1800018bd  mov     eax, edi
0x1800018bf  mov     rbx, [r11+10h]
0x1800018c3  mov     rsi, [r11+18h]
0x1800018c7  mov     rsp, r11
0x1800018ca  pop     rdi
0x1800018cb  retn
```
