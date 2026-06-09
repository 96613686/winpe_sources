# CDDSYNCOBJECT::Create(CddBitmap *)

- ea: `0x14001ef90`
- end: `0x14001f267`
- name: `?Create@CDDSYNCOBJECT@@QEAAJPEAVCddBitmap@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(CDDSYNCOBJECT *__hidden this, struct CddBitmap *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001b170`

## callees

- `0x14001ef90`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14001efdc`
- `ntoskrnl!KeStackAttachProcess` at `0x14001efdc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001f235`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001f235`
- `ntoskrnl!DbgPrint` at `0x14001f005`
- `ntoskrnl!DbgPrint` at `0x14001f07c`
- `ntoskrnl!DbgPrint` at `0x14001f180`
- `ntoskrnl!DbgPrint` at `0x14001f005`
- `ntoskrnl!DbgPrint` at `0x14001f07c`
- `ntoskrnl!DbgPrint` at `0x14001f180`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001eff2`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001f069`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001f169`
- `watchdog!WdLogSingleEntry2` at `0x14001f1e5`
- `watchdog!WdLogSingleEntry2` at `0x14001f1e5`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f02c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f0a3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f1a8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f1fc`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f02c`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f0a3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f1a8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001f1fc`
- `watchdog!WdLogSingleEntry0` at `0x14001f016`
- `watchdog!WdLogSingleEntry0` at `0x14001f08d`
- `watchdog!WdLogSingleEntry0` at `0x14001f191`
- `watchdog!WdLogSingleEntry0` at `0x14001f016`
- `watchdog!WdLogSingleEntry0` at `0x14001f08d`
- `watchdog!WdLogSingleEntry0` at `0x14001f191`

## pseudocode

```c
__int64 __fastcall CDDSYNCOBJECT::Create(CDDSYNCOBJECT *this, struct CddBitmap *a2)
{
  __int64 v2; // rdi
  struct _KPROCESS *v5; // rcx
  int v6; // esi
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  bool v13; // zf
  int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rdx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  _DWORD v23[24]; // [rsp+20h] [rbp-69h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+80h] [rbp-9h] BYREF
  char v25; // [rsp+B0h] [rbp+27h]

  v2 = *((_QWORD *)a2 + 1);
  v5 = *(struct _KPROCESS **)(v2 + 752);
  v6 = 1;
  v25 = 0;
  if ( v5 )
  {
    KeStackAttachProcess(v5, &ApcState);
    v25 = 1;
  }
  if ( *((_DWORD *)this + 1) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("m_hSyncObjectGdi must be NULL");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 5497;
    v9 = (_QWORD *)WdLogNewEntry5_WdError(v8, v7);
    v9[3] = gCddImageInfo;
    v9[4] = (unsigned int)dword_14003E570;
    v9[5] = 215857758;
    WdLogGlobalForLineNumber = 5497;
    __debugbreak();
  }
  if ( !*(_DWORD *)(v2 + 2520) && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("hDevice is NULL");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 5498;
    v12 = (_QWORD *)WdLogNewEntry5_WdError(v11, v10);
    v12[3] = gCddImageInfo;
    v12[4] = (unsigned int)dword_14003E570;
    v12[5] = 215857758;
    WdLogGlobalForLineNumber = 5498;
    __debugbreak();
  }
  memset(v23, 0, sizeof(v23));
  v13 = *((_BYTE *)a2 + 128) >= 0;
  v23[0] = *(_DWORD *)(v2 + 2520);
  if ( !v13 )
    v6 = 5;
  v23[2] = 3;
  v23[3] = v6;
  v14 = (*(__int64 (__fastcall **)(_DWORD *))(v2 + 352))(v23);
  v15 = v14;
  if ( v14 < 0 )
  {
    WdLogSingleEntry2(2, v14, v2);
    WdLogGlobalForLineNumber = 5524;
    v21 = (_QWORD *)WdLogNewEntry5_WdError(v20, v19);
    v21[3] = gCddImageInfo;
    v21[4] = (unsigned int)dword_14003E570;
    v21[5] = 215857758;
    WdLogGlobalForLineNumber = 5524;
  }
  else
  {
    *(_DWORD *)this = v23[20];
    *((_DWORD *)this + 1) = v23[22];
    *((_QWORD *)this + 2) = a2;
    *((_QWORD *)this + 1) = 0;
    *((_DWORD *)this + 74) = 0;
    *((_DWORD *)this + 6) = 0;
    memset((char *)this + 28, 0, 0x104u);
    *((_QWORD *)this + 36) = 0;
    if ( (!*((_DWORD *)this + 1) || !*(_DWORD *)this) && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint(byte_14003A04E);
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 5520;
      v18 = (_QWORD *)WdLogNewEntry5_WdError(v17, v16);
      v18[3] = gCddImageInfo;
      v18[4] = (unsigned int)dword_14003E570;
      v18[5] = 215857758;
      WdLogGlobalForLineNumber = 5520;
      __debugbreak();
    }
  }
  if ( v25 )
    KeUnstackDetachProcess(&ApcState);
  return v15;
}

```

## disassembly

```asm
0x14001ef90  mov     [rsp-8+arg_10], rbx
0x14001ef95  push    rbp
0x14001ef96  push    rsi
0x14001ef97  push    rdi
0x14001ef98  push    r12
0x14001ef9a  push    r14
0x14001ef9c  lea     rbp, [rsp-37h]
0x14001efa1  sub     rsp, 0C0h
0x14001efa8  mov     rax, cs:__security_cookie
0x14001efaf  xor     rax, rsp
0x14001efb2  mov     [rbp+57h+var_28], rax
0x14001efb6  mov     rdi, [rdx+8]
0x14001efba  xor     r12d, r12d
0x14001efbd  mov     rbx, rcx
0x14001efc0  mov     r14, rdx
0x14001efc3  mov     rcx, [rdi+2F0h]; PROCESS
0x14001efca  lea     esi, [r12+1]
0x14001efcf  mov     [rbp+57h+var_30], r12b
0x14001efd3  test    rcx, rcx
0x14001efd6  jz      short loc_14001EFEC
0x14001efd8  lea     rdx, [rbp+57h+ApcState]; ApcState
0x14001efdc  call    cs:__imp_KeStackAttachProcess
0x14001efe3  nop     dword ptr [rax+rax+00h]
0x14001efe8  mov     [rbp+57h+var_30], sil
0x14001efec  cmp     [rbx+4], r12d
0x14001eff0  jz      short loc_14001F060
0x14001eff2  mov     rax, cs:KdDebuggerEnabled
0x14001eff9  cmp     [rax], r12b
0x14001effc  jz      short loc_14001F060
0x14001effe  lea     rcx, aMHsyncobjectgd; "m_hSyncObjectGdi must be NULL"
0x14001f005  call    cs:__imp_DbgPrint
0x14001f00c  nop     dword ptr [rax+rax+00h]
0x14001f011  mov     ecx, 2
0x14001f016  call    cs:__imp_WdLogSingleEntry0
0x14001f01d  nop     dword ptr [rax+rax+00h]
0x14001f022  mov     cs:WdLogGlobalForLineNumber, 1579h
0x14001f02c  call    cs:__imp_WdLogNewEntry5_WdError
0x14001f033  nop     dword ptr [rax+rax+00h]
0x14001f038  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f03f  mov     [rax+18h], rcx
0x14001f043  mov     ecx, cs:dword_14003E570
0x14001f049  mov     [rax+20h], rcx
0x14001f04d  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f055  mov     cs:WdLogGlobalForLineNumber, 1579h
0x14001f05f  int     3; Trap to Debugger
0x14001f060  cmp     [rdi+9D8h], r12d
0x14001f067  jnz     short loc_14001F0D7
0x14001f069  mov     rax, cs:KdDebuggerEnabled
0x14001f070  cmp     [rax], r12b
0x14001f073  jz      short loc_14001F0D7
0x14001f075  lea     rcx, aHdeviceIsNull; "hDevice is NULL"
0x14001f07c  call    cs:__imp_DbgPrint
0x14001f083  nop     dword ptr [rax+rax+00h]
0x14001f088  mov     ecx, 2
0x14001f08d  call    cs:__imp_WdLogSingleEntry0
0x14001f094  nop     dword ptr [rax+rax+00h]
0x14001f099  mov     cs:WdLogGlobalForLineNumber, 157Ah
0x14001f0a3  call    cs:__imp_WdLogNewEntry5_WdError
0x14001f0aa  nop     dword ptr [rax+rax+00h]
0x14001f0af  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f0b6  mov     [rax+18h], rcx
0x14001f0ba  mov     ecx, cs:dword_14003E570
0x14001f0c0  mov     [rax+20h], rcx
0x14001f0c4  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f0cc  mov     cs:WdLogGlobalForLineNumber, 157Ah
0x14001f0d6  int     3; Trap to Debugger
0x14001f0d7  xor     edx, edx; Val
0x14001f0d9  lea     rcx, [rbp+57h+var_C0]; void *
0x14001f0dd  lea     r8d, [rdx+60h]; Size
0x14001f0e1  call    memset
0x14001f0e6  mov     eax, [rdi+9D8h]
0x14001f0ec  lea     rcx, [rbp+57h+var_C0]
0x14001f0f0  test    byte ptr [r14+80h], 80h
0x14001f0f8  mov     [rbp+57h+var_C0], eax
0x14001f0fb  mov     eax, 5
0x14001f100  cmovnz  esi, eax
0x14001f103  mov     [rbp+57h+var_B8], 3
0x14001f10a  mov     [rbp+57h+var_B4], esi
0x14001f10d  mov     rax, [rdi+160h]
0x14001f114  call    _guard_dispatch_icall
0x14001f119  movsxd  rsi, eax
0x14001f11c  test    eax, eax
0x14001f11e  js      loc_14001F1DA
0x14001f124  mov     ecx, [rbp+57h+var_70]
0x14001f127  xor     edx, edx; Val
0x14001f129  mov     [rbx], ecx
0x14001f12b  mov     r8d, 104h; Size
0x14001f131  mov     ecx, [rbp+57h+var_68]
0x14001f134  mov     [rbx+4], ecx
0x14001f137  lea     rcx, [rbx+1Ch]; void *
0x14001f13b  mov     [rbx+10h], r14
0x14001f13f  mov     [rbx+8], r12
0x14001f143  mov     [rbx+128h], r12d
0x14001f14a  mov     [rbx+18h], r12d
0x14001f14e  call    memset
0x14001f153  mov     [rbx+120h], r12
0x14001f15a  cmp     [rbx+4], r12d
0x14001f15e  jz      short loc_14001F169
0x14001f160  cmp     [rbx], r12d
0x14001f163  jnz     loc_14001F22B
0x14001f169  mov     rax, cs:KdDebuggerEnabled
0x14001f170  cmp     [rax], r12b
0x14001f173  jz      loc_14001F22B
0x14001f179  lea     rcx, byte_14003A04E; Format
0x14001f180  call    cs:__imp_DbgPrint
0x14001f187  nop     dword ptr [rax+rax+00h]
0x14001f18c  mov     ecx, 2
0x14001f191  call    cs:__imp_WdLogSingleEntry0
0x14001f198  nop     dword ptr [rax+rax+00h]
0x14001f19d  mov     ebx, 1590h
0x14001f1a2  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f1a8  call    cs:__imp_WdLogNewEntry5_WdError
0x14001f1af  nop     dword ptr [rax+rax+00h]
0x14001f1b4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f1bb  mov     [rax+18h], rcx
0x14001f1bf  mov     ecx, cs:dword_14003E570
0x14001f1c5  mov     [rax+20h], rcx
0x14001f1c9  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f1d1  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f1d7  int     3; Trap to Debugger
0x14001f1d8  jmp     short loc_14001F22B
0x14001f1da  mov     rdx, rsi
0x14001f1dd  mov     r8, rdi
0x14001f1e0  mov     ecx, 2
0x14001f1e5  call    cs:__imp_WdLogSingleEntry2
0x14001f1ec  nop     dword ptr [rax+rax+00h]
0x14001f1f1  mov     ebx, 1594h
0x14001f1f6  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f1fc  call    cs:__imp_WdLogNewEntry5_WdError
0x14001f203  nop     dword ptr [rax+rax+00h]
0x14001f208  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f20f  mov     [rax+18h], rcx
0x14001f213  mov     ecx, cs:dword_14003E570
0x14001f219  mov     [rax+20h], rcx
0x14001f21d  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f225  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001f22b  cmp     [rbp+57h+var_30], r12b
0x14001f22f  jz      short loc_14001F241
0x14001f231  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14001f235  call    cs:__imp_KeUnstackDetachProcess
0x14001f23c  nop     dword ptr [rax+rax+00h]
0x14001f241  mov     eax, esi
0x14001f243  mov     rcx, [rbp+57h+var_28]
0x14001f247  xor     rcx, rsp; StackCookie
0x14001f24a  call    __security_check_cookie
0x14001f24f  mov     rbx, [rsp+0E0h+arg_10]
0x14001f257  add     rsp, 0C0h
0x14001f25e  pop     r14
0x14001f260  pop     r12
0x14001f262  pop     rdi
0x14001f263  pop     rsi
0x14001f264  pop     rbp
0x14001f265  retn
```
