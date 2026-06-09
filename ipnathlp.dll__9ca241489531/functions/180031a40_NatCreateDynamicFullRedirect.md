# NatCreateDynamicFullRedirect

- ea: `0x180031a40`
- end: `0x180031c4a`
- name: `NatCreateDynamicFullRedirect`
- size: `522`
- prototype: `__int64 __fastcall(int, char, int, __int16, int, __int16, int, __int16, int, __int16, int, int, int, _QWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d670`
- `0x180056fb0`
- `0x180057020`
- `0x180081ee0`

## callees

- `0x180031a40`
- `0x180031c50`
- `0x180032024`
- `0x18004bc74`
- `0x18004bff8`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031ae2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031af3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031af3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031c08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031c08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180031b1c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180031b1c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180031bf4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180031bf4`

## string_xrefs

- `0x180031bed`: `ipnathlp.dll`

## pseudocode

```c
__int64 __fastcall NatCreateDynamicFullRedirect(
        int a1,
        char a2,
        int a3,
        __int16 a4,
        int a5,
        __int16 a6,
        int a7,
        __int16 a8,
        int a9,
        __int16 a10,
        int a11,
        int a12,
        int a13,
        _QWORD *a14)
{
  int v18; // r12d
  int v19; // eax
  HANDLE ProcessHeap; // rax
  char *v21; // rax
  char *v22; // rbx
  __int64 result; // rax
  int v24; // eax
  unsigned int v25; // edi
  unsigned int i; // edi

  if ( !a14 )
    return 87;
  v18 = a12;
  v19 = a11;
  if ( (a1 & 0x10) == 0 )
    v19 = a5;
  if ( !(unsigned __int8)NatValidateRedirectParameters(a1, a2, a3, a4, v19, a6, a7, a8, a9, a10, a12) )
    return 87;
  ProcessHeap = GetProcessHeap();
  v21 = (char *)HeapAlloc(ProcessHeap, 0, 0x90u);
  v22 = v21;
  if ( !v21 )
    return 8;
  memset_0(v21, 0, 0x90u);
  InitializeCriticalSection((LPCRITICAL_SECTION)v22);
  *((_DWORD *)v22 + 10) = 1;
  *((_QWORD *)v22 + 9) = v22 + 64;
  *((_QWORD *)v22 + 8) = v22 + 64;
  v24 = a13;
  *((_QWORD *)v22 + 6) = 0;
  if ( !a13 )
    v24 = 5;
  v22[104] = a2;
  *((_DWORD *)v22 + 14) = v24;
  *((_DWORD *)v22 + 29) = a3;
  *((_DWORD *)v22 + 20) = a1 | 1;
  *((_DWORD *)v22 + 27) = a5;
  *((_WORD *)v22 + 56) = a6;
  *((_DWORD *)v22 + 33) = a7;
  *((_WORD *)v22 + 68) = a8;
  *((_DWORD *)v22 + 31) = a9;
  *((_WORD *)v22 + 64) = a10;
  if ( (a1 & 0x400) == 0 )
    v18 = -1;
  *((_WORD *)v22 + 60) = a4;
  *((_DWORD *)v22 + 25) = v18;
  *((_DWORD *)v22 + 24) = a11;
  v25 = NatOpenDriver((PHANDLE)v22 + 6);
  if ( v25 )
  {
    NatCleanupDynamicRedirect((LPCRITICAL_SECTION)v22);
    return v25;
  }
  else
  {
    if ( !_InterlockedExchange(&DllReferenceAdded, 1) && !LoadLibraryW(L"ipnathlp.dll") )
      _InterlockedExchange(&DllReferenceAdded, 0);
    EnterCriticalSection((LPCRITICAL_SECTION)v22);
    for ( i = 0; i < *((_DWORD *)v22 + 14); ++i )
      NatCreateDynamicRedirectInstance((LPCRITICAL_SECTION)v22);
    LeaveCriticalSection((LPCRITICAL_SECTION)v22);
    result = 0;
    *a14 = v22;
  }
  return result;
}

```

## disassembly

```asm
0x180031a40  push    rbx
0x180031a42  push    rbp
0x180031a43  push    rsi
0x180031a44  push    rdi
0x180031a45  push    r12
0x180031a47  push    r13
0x180031a49  push    r14
0x180031a4b  push    r15
0x180031a4d  sub     rsp, 68h
0x180031a51  mov     rsi, [rsp+0A8h+arg_68]
0x180031a59  movzx   ebp, r9w
0x180031a5d  mov     r14d, r8d
0x180031a60  mov     r15b, dl
0x180031a63  mov     edi, ecx
0x180031a65  test    rsi, rsi
0x180031a68  jz      loc_180031C34
0x180031a6e  movzx   ecx, [rsp+0A8h+arg_48]
0x180031a76  test    dil, 10h
0x180031a7a  mov     r12d, [rsp+0A8h+arg_58]
0x180031a82  mov     r13d, [rsp+0A8h+arg_50]
0x180031a8a  mov     eax, r13d
0x180031a8d  cmovz   eax, [rsp+0A8h+arg_20]
0x180031a95  mov     [rsp+0A8h+var_58], r12d
0x180031a9a  mov     [rsp+0A8h+var_60], cx
0x180031a9f  mov     ecx, [rsp+0A8h+arg_40]
0x180031aa6  mov     [rsp+0A8h+var_68], ecx
0x180031aaa  movzx   ecx, [rsp+0A8h+arg_38]
0x180031ab2  mov     [rsp+0A8h+var_70], cx
0x180031ab7  mov     ecx, [rsp+0A8h+arg_30]
0x180031abe  mov     [rsp+0A8h+var_78], ecx
0x180031ac2  movzx   ecx, [rsp+0A8h+arg_28]
0x180031aca  mov     [rsp+0A8h+var_80], cx
0x180031acf  mov     ecx, edi
0x180031ad1  mov     [rsp+0A8h+var_88], eax
0x180031ad5  call    NatValidateRedirectParameters
0x180031ada  test    al, al
0x180031adc  jz      loc_180031C34
0x180031ae2  call    cs:__imp_GetProcessHeap
0x180031ae8  xor     edx, edx; dwFlags
0x180031aea  mov     r8d, 90h; dwBytes
0x180031af0  mov     rcx, rax; hHeap
0x180031af3  call    cs:__imp_HeapAlloc
0x180031af9  mov     rbx, rax
0x180031afc  test    rax, rax
0x180031aff  jnz     short loc_180031B09
0x180031b01  lea     eax, [rbx+8]
0x180031b04  jmp     loc_180031C39
0x180031b09  xor     edx, edx; Val
0x180031b0b  mov     r8d, 90h; Size
0x180031b11  mov     rcx, rbx; void *
0x180031b14  call    memset_0
0x180031b19  mov     rcx, rbx; lpCriticalSection
0x180031b1c  call    cs:__imp_InitializeCriticalSection
0x180031b22  lea     rax, [rbx+40h]
0x180031b26  mov     dword ptr [rbx+28h], 1
0x180031b2d  mov     [rax+8], rax
0x180031b31  lea     rcx, [rbx+30h]; FileHandle
0x180031b35  mov     [rax], rax
0x180031b38  mov     edx, 5
0x180031b3d  mov     eax, [rsp+0A8h+arg_60]
0x180031b44  test    eax, eax
0x180031b46  mov     qword ptr [rcx], 0
0x180031b4d  cmovz   eax, edx
0x180031b50  mov     [rbx+68h], r15b
0x180031b54  mov     [rbx+38h], eax
0x180031b57  mov     eax, edi
0x180031b59  or      eax, 1
0x180031b5c  mov     [rbx+74h], r14d
0x180031b60  mov     [rbx+50h], eax
0x180031b63  bt      edi, 0Ah
0x180031b67  mov     eax, [rsp+0A8h+arg_20]
0x180031b6e  mov     [rbx+6Ch], eax
0x180031b71  movzx   eax, [rsp+0A8h+arg_28]
0x180031b79  mov     [rbx+70h], ax
0x180031b7d  mov     eax, [rsp+0A8h+arg_30]
0x180031b84  mov     [rbx+84h], eax
0x180031b8a  movzx   eax, [rsp+0A8h+arg_38]
0x180031b92  mov     [rbx+88h], ax
0x180031b99  mov     eax, [rsp+0A8h+arg_40]
0x180031ba0  mov     [rbx+7Ch], eax
0x180031ba3  movzx   eax, [rsp+0A8h+arg_48]
0x180031bab  mov     [rbx+80h], ax
0x180031bb2  mov     eax, 0FFFFFFFFh
0x180031bb7  cmovnb  r12d, eax
0x180031bbb  mov     [rbx+78h], bp
0x180031bbf  mov     [rbx+64h], r12d
0x180031bc3  mov     [rbx+60h], r13d
0x180031bc7  call    NatOpenDriver
0x180031bcc  mov     edi, eax
0x180031bce  test    eax, eax
0x180031bd0  jz      short loc_180031BDE
0x180031bd2  mov     rcx, rbx; lpCriticalSection
0x180031bd5  call    NatCleanupDynamicRedirect
0x180031bda  mov     eax, edi
0x180031bdc  jmp     short loc_180031C39
0x180031bde  mov     eax, 1
0x180031be3  xchg    eax, cs:DllReferenceAdded
0x180031be9  test    eax, eax
0x180031beb  jnz     short loc_180031C05
0x180031bed  lea     rcx, aIpnathlpDll_0; "ipnathlp.dll"
0x180031bf4  call    cs:__imp_LoadLibraryW
0x180031bfa  test    rax, rax
0x180031bfd  jnz     short loc_180031C05
0x180031bff  xchg    eax, cs:DllReferenceAdded
0x180031c05  mov     rcx, rbx; lpCriticalSection
0x180031c08  call    cs:__imp_EnterCriticalSection
0x180031c0e  xor     edi, edi
0x180031c10  cmp     [rbx+38h], edi
0x180031c13  jbe     short loc_180031C24
0x180031c15  mov     rcx, rbx; lpCriticalSection
0x180031c18  call    NatCreateDynamicRedirectInstance
0x180031c1d  inc     edi
0x180031c1f  cmp     edi, [rbx+38h]
0x180031c22  jb      short loc_180031C15
0x180031c24  mov     rcx, rbx; lpCriticalSection
0x180031c27  call    cs:__imp_LeaveCriticalSection
0x180031c2d  xor     eax, eax
0x180031c2f  mov     [rsi], rbx
0x180031c32  jmp     short loc_180031C39
0x180031c34  mov     eax, 57h ; 'W'
0x180031c39  add     rsp, 68h
0x180031c3d  pop     r15
0x180031c3f  pop     r14
0x180031c41  pop     r13
0x180031c43  pop     r12
0x180031c45  pop     rdi
0x180031c46  pop     rsi
0x180031c47  pop     rbp
0x180031c48  pop     rbx
0x180031c49  retn
```
