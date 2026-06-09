# NatCreateDynamicFullRedirect

- ea: `0x1800340f0`
- end: `0x18003431f`
- name: `NatCreateDynamicFullRedirect`
- size: `559`
- prototype: `__int64 __fastcall(int, char, int, __int16, int, __int16, int, __int16, int, __int16, int, int, int, _QWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800514c0`
- `0x18005b450`
- `0x18005b4d0`
- `0x180088570`

## callees

- `0x1800340f0`
- `0x180034328`
- `0x18003477c`
- `0x18004f880`
- `0x18004fcf8`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034192`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034192`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800341a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800341a9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342f5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800341d8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800341d8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800342b6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800342b6`

## string_xrefs

- `0x1800342af`: `ipnathlp.dll`

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
0x1800340f0  push    rbx
0x1800340f2  push    rbp
0x1800340f3  push    rsi
0x1800340f4  push    rdi
0x1800340f5  push    r12
0x1800340f7  push    r13
0x1800340f9  push    r14
0x1800340fb  push    r15
0x1800340fd  sub     rsp, 68h
0x180034101  mov     rsi, [rsp+0A8h+arg_68]
0x180034109  movzx   ebp, r9w
0x18003410d  mov     r14d, r8d
0x180034110  mov     r15b, dl
0x180034113  mov     edi, ecx
0x180034115  test    rsi, rsi
0x180034118  jz      loc_180034308
0x18003411e  movzx   ecx, [rsp+0A8h+arg_48]
0x180034126  test    dil, 10h
0x18003412a  mov     r12d, [rsp+0A8h+arg_58]
0x180034132  mov     r13d, [rsp+0A8h+arg_50]
0x18003413a  mov     eax, r13d
0x18003413d  cmovz   eax, [rsp+0A8h+arg_20]
0x180034145  mov     [rsp+0A8h+var_58], r12d
0x18003414a  mov     [rsp+0A8h+var_60], cx
0x18003414f  mov     ecx, [rsp+0A8h+arg_40]
0x180034156  mov     [rsp+0A8h+var_68], ecx
0x18003415a  movzx   ecx, [rsp+0A8h+arg_38]
0x180034162  mov     [rsp+0A8h+var_70], cx
0x180034167  mov     ecx, [rsp+0A8h+arg_30]
0x18003416e  mov     [rsp+0A8h+var_78], ecx
0x180034172  movzx   ecx, [rsp+0A8h+arg_28]
0x18003417a  mov     [rsp+0A8h+var_80], cx
0x18003417f  mov     ecx, edi
0x180034181  mov     [rsp+0A8h+var_88], eax
0x180034185  call    NatValidateRedirectParameters
0x18003418a  test    al, al
0x18003418c  jz      loc_180034308
0x180034192  call    cs:__imp_GetProcessHeap
0x180034199  nop     dword ptr [rax+rax+00h]
0x18003419e  xor     edx, edx; dwFlags
0x1800341a0  mov     r8d, 90h; dwBytes
0x1800341a6  mov     rcx, rax; hHeap
0x1800341a9  call    cs:__imp_HeapAlloc
0x1800341b0  nop     dword ptr [rax+rax+00h]
0x1800341b5  mov     rbx, rax
0x1800341b8  test    rax, rax
0x1800341bb  jnz     short loc_1800341C5
0x1800341bd  lea     eax, [rbx+8]
0x1800341c0  jmp     loc_18003430D
0x1800341c5  xor     edx, edx; Val
0x1800341c7  mov     r8d, 90h; Size
0x1800341cd  mov     rcx, rbx; void *
0x1800341d0  call    memset_0
0x1800341d5  mov     rcx, rbx; lpCriticalSection
0x1800341d8  call    cs:__imp_InitializeCriticalSection
0x1800341df  nop     dword ptr [rax+rax+00h]
0x1800341e4  lea     rax, [rbx+40h]
0x1800341e8  mov     dword ptr [rbx+28h], 1
0x1800341ef  mov     [rax+8], rax
0x1800341f3  lea     rcx, [rbx+30h]; FileHandle
0x1800341f7  mov     [rax], rax
0x1800341fa  mov     edx, 5
0x1800341ff  mov     eax, [rsp+0A8h+arg_60]
0x180034206  test    eax, eax
0x180034208  mov     qword ptr [rcx], 0
0x18003420f  cmovz   eax, edx
0x180034212  mov     [rbx+68h], r15b
0x180034216  mov     [rbx+38h], eax
0x180034219  mov     eax, edi
0x18003421b  or      eax, 1
0x18003421e  mov     [rbx+74h], r14d
0x180034222  mov     [rbx+50h], eax
0x180034225  bt      edi, 0Ah
0x180034229  mov     eax, [rsp+0A8h+arg_20]
0x180034230  mov     [rbx+6Ch], eax
0x180034233  movzx   eax, [rsp+0A8h+arg_28]
0x18003423b  mov     [rbx+70h], ax
0x18003423f  mov     eax, [rsp+0A8h+arg_30]
0x180034246  mov     [rbx+84h], eax
0x18003424c  movzx   eax, [rsp+0A8h+arg_38]
0x180034254  mov     [rbx+88h], ax
0x18003425b  mov     eax, [rsp+0A8h+arg_40]
0x180034262  mov     [rbx+7Ch], eax
0x180034265  movzx   eax, [rsp+0A8h+arg_48]
0x18003426d  mov     [rbx+80h], ax
0x180034274  mov     eax, 0FFFFFFFFh
0x180034279  cmovnb  r12d, eax
0x18003427d  mov     [rbx+78h], bp
0x180034281  mov     [rbx+64h], r12d
0x180034285  mov     [rbx+60h], r13d
0x180034289  call    NatOpenDriver
0x18003428e  mov     edi, eax
0x180034290  test    eax, eax
0x180034292  jz      short loc_1800342A0
0x180034294  mov     rcx, rbx; lpCriticalSection
0x180034297  call    NatCleanupDynamicRedirect
0x18003429c  mov     eax, edi
0x18003429e  jmp     short loc_18003430D
0x1800342a0  mov     eax, 1
0x1800342a5  xchg    eax, cs:DllReferenceAdded
0x1800342ab  test    eax, eax
0x1800342ad  jnz     short loc_1800342CD
0x1800342af  lea     rcx, aIpnathlpDll_0; "ipnathlp.dll"
0x1800342b6  call    cs:__imp_LoadLibraryW
0x1800342bd  nop     dword ptr [rax+rax+00h]
0x1800342c2  test    rax, rax
0x1800342c5  jnz     short loc_1800342CD
0x1800342c7  xchg    eax, cs:DllReferenceAdded
0x1800342cd  mov     rcx, rbx; lpCriticalSection
0x1800342d0  call    cs:__imp_EnterCriticalSection
0x1800342d7  nop     dword ptr [rax+rax+00h]
0x1800342dc  xor     edi, edi
0x1800342de  cmp     [rbx+38h], edi
0x1800342e1  jbe     short loc_1800342F2
0x1800342e3  mov     rcx, rbx; lpCriticalSection
0x1800342e6  call    NatCreateDynamicRedirectInstance
0x1800342eb  inc     edi
0x1800342ed  cmp     edi, [rbx+38h]
0x1800342f0  jb      short loc_1800342E3
0x1800342f2  mov     rcx, rbx; lpCriticalSection
0x1800342f5  call    cs:__imp_LeaveCriticalSection
0x1800342fc  nop     dword ptr [rax+rax+00h]
0x180034301  xor     eax, eax
0x180034303  mov     [rsi], rbx
0x180034306  jmp     short loc_18003430D
0x180034308  mov     eax, 57h ; 'W'
0x18003430d  add     rsp, 68h
0x180034311  pop     r15
0x180034313  pop     r14
0x180034315  pop     r13
0x180034317  pop     r12
0x180034319  pop     rdi
0x18003431a  pop     rsi
0x18003431b  pop     rbp
0x18003431c  pop     rbx
0x18003431d  retn
```
