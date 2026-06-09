# CAsyncHttp::HrInit(char *,ushort,ulong)

- ea: `0x1800a6f84`
- end: `0x1800a710b`
- name: `?HrInit@CAsyncHttp@@QEAAJPEADGK@Z`
- size: `391`
- prototype: `__int64 __fastcall(CAsyncHttp *__hidden this, char *, unsigned __int16, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ae020`
- `0x1800af5c0`

## callees

- `0x180012cd0`
- `0x1800a67ac`
- `0x1800a6900`
- `0x1800a6b8c`
- `0x1800a6f84`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800a6fe9`
- `KERNEL32!CloseHandle` at `0x1800a6ffc`
- `KERNEL32!CloseHandle` at `0x1800a6fe9`
- `KERNEL32!CloseHandle` at `0x1800a6ffc`
- `KERNEL32!GetLastError` at `0x1800a70da`
- `KERNEL32!GetLastError` at `0x1800a70da`
- `KERNEL32!LeaveCriticalSection` at `0x1800a70f6`
- `KERNEL32!LeaveCriticalSection` at `0x1800a70f6`
- `KERNEL32!EnterCriticalSection` at `0x1800a6fca`
- `KERNEL32!EnterCriticalSection` at `0x1800a6fca`
- `KERNEL32!CreateEventA` at `0x1800a70ab`
- `KERNEL32!CreateEventA` at `0x1800a70c4`
- `KERNEL32!CreateEventA` at `0x1800a70ab`
- `KERNEL32!CreateEventA` at `0x1800a70c4`

## pseudocode

```c
__int64 __fastcall CAsyncHttp::HrInit(CAsyncHttp *this, char *a2, __int16 a3, int a4)
{
  void *v9; // rcx
  void *v10; // rcx
  signed int v11; // edi
  HANDLE EventA; // rax
  signed int LastError; // eax

  if ( !a2 )
    return 2147942487LL;
  if ( *((_DWORD *)this + 26) && *((_DWORD *)this + 26) != 10 )
    return 2148322307LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  CAsyncHttp::Close(this);
  CAsyncHttp::CloseSession(this);
  v9 = (void *)*((_QWORD *)this + 11);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 11) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 12);
  if ( v10 )
  {
    CloseHandle(v10);
    *((_QWORD *)this + 12) = 0;
  }
  if ( !*((_QWORD *)this + 348) )
    CAsyncHttp::CreateWnd(this);
  if ( *((_QWORD *)this + 342) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 342) = 0;
  }
  if ( *((_QWORD *)this + 345) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 345) = 0;
  }
  *((_BYTE *)this + 398) = 0;
  *((_BYTE *)this + 2446) = 0;
  v11 = StringCchCopyA((char *)this + 142, 0x100u, a2);
  if ( v11 >= 0 )
  {
    if ( a3 )
      *((_WORD *)this + 70) = a3;
    if ( a4 )
      *((_DWORD *)this + 34) = a4;
    EventA = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 11) = EventA;
    if ( EventA )
      *((_QWORD *)this + 12) = CreateEventA(0, 0, 0, 0);
    if ( !*((_QWORD *)this + 11) || !*((_QWORD *)this + 12) )
    {
      LastError = GetLastError();
      *((_DWORD *)this + 29) = LastError;
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a6f84  push    rbx
0x1800a6f86  push    rbp
0x1800a6f87  push    rsi
0x1800a6f88  push    rdi
0x1800a6f89  push    r14
0x1800a6f8b  push    r15
0x1800a6f8d  sub     rsp, 28h
0x1800a6f91  xor     r15d, r15d
0x1800a6f94  mov     esi, r9d
0x1800a6f97  movzx   ebp, r8w
0x1800a6f9b  mov     rdi, rdx
0x1800a6f9e  mov     rbx, rcx
0x1800a6fa1  test    rdx, rdx
0x1800a6fa4  jnz     short loc_1800A6FB0
0x1800a6fa6  mov     eax, 80070057h
0x1800a6fab  jmp     loc_1800A70FE
0x1800a6fb0  cmp     [rcx+68h], r15d
0x1800a6fb4  jz      short loc_1800A6FC6
0x1800a6fb6  cmp     dword ptr [rcx+68h], 0Ah
0x1800a6fba  jz      short loc_1800A6FC6
0x1800a6fbc  mov     eax, 800CCC03h
0x1800a6fc1  jmp     loc_1800A70FE
0x1800a6fc6  add     rcx, 10h; lpCriticalSection
0x1800a6fca  call    cs:__imp_EnterCriticalSection
0x1800a6fd0  mov     rcx, rbx; this
0x1800a6fd3  call    ?Close@CAsyncHttp@@QEAAJXZ; CAsyncHttp::Close(void)
0x1800a6fd8  mov     rcx, rbx; this
0x1800a6fdb  call    ?CloseSession@CAsyncHttp@@QEAAXXZ; CAsyncHttp::CloseSession(void)
0x1800a6fe0  mov     rcx, [rbx+58h]; hObject
0x1800a6fe4  test    rcx, rcx
0x1800a6fe7  jz      short loc_1800A6FF3
0x1800a6fe9  call    cs:__imp_CloseHandle
0x1800a6fef  mov     [rbx+58h], r15
0x1800a6ff3  mov     rcx, [rbx+60h]; hObject
0x1800a6ff7  test    rcx, rcx
0x1800a6ffa  jz      short loc_1800A7006
0x1800a6ffc  call    cs:__imp_CloseHandle
0x1800a7002  mov     [rbx+60h], r15
0x1800a7006  cmp     [rbx+0AE0h], r15
0x1800a700d  jnz     short loc_1800A7017
0x1800a700f  mov     rcx, rbx; this
0x1800a7012  call    ?CreateWnd@CAsyncHttp@@AEAAPEAUHWND__@@XZ; CAsyncHttp::CreateWnd(void)
0x1800a7017  mov     rdx, [rbx+0AB0h]
0x1800a701e  test    rdx, rdx
0x1800a7021  jz      short loc_1800A703D
0x1800a7023  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800a702a  mov     rax, [rcx]
0x1800a702d  mov     rax, [rax+28h]
0x1800a7031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7036  mov     [rbx+0AB0h], r15
0x1800a703d  mov     rdx, [rbx+0AC8h]
0x1800a7044  test    rdx, rdx
0x1800a7047  jz      short loc_1800A7063
0x1800a7049  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800a7050  mov     rax, [rcx]
0x1800a7053  mov     rax, [rax+28h]
0x1800a7057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a705c  mov     [rbx+0AC8h], r15
0x1800a7063  lea     rcx, [rbx+8Eh]; char *
0x1800a706a  mov     [rbx+18Eh], r15b
0x1800a7071  mov     r8, rdi; char *
0x1800a7074  mov     [rbx+98Eh], r15b
0x1800a707b  mov     edx, 100h; unsigned __int64
0x1800a7080  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800a7085  mov     edi, eax
0x1800a7087  test    eax, eax
0x1800a7089  js      short loc_1800A70F2
0x1800a708b  test    bp, bp
0x1800a708e  jz      short loc_1800A7097
0x1800a7090  mov     [rbx+8Ch], bp
0x1800a7097  test    esi, esi
0x1800a7099  jz      short loc_1800A70A1
0x1800a709b  mov     [rbx+88h], esi
0x1800a70a1  xor     r9d, r9d; lpName
0x1800a70a4  xor     r8d, r8d; bInitialState
0x1800a70a7  xor     edx, edx; bManualReset
0x1800a70a9  xor     ecx, ecx; lpEventAttributes
0x1800a70ab  call    cs:__imp_CreateEventA
0x1800a70b1  mov     [rbx+58h], rax
0x1800a70b5  test    rax, rax
0x1800a70b8  jz      short loc_1800A70CE
0x1800a70ba  xor     r9d, r9d; lpName
0x1800a70bd  xor     r8d, r8d; bInitialState
0x1800a70c0  xor     edx, edx; bManualReset
0x1800a70c2  xor     ecx, ecx; lpEventAttributes
0x1800a70c4  call    cs:__imp_CreateEventA
0x1800a70ca  mov     [rbx+60h], rax
0x1800a70ce  cmp     [rbx+58h], r15
0x1800a70d2  jz      short loc_1800A70DA
0x1800a70d4  cmp     [rbx+60h], r15
0x1800a70d8  jnz     short loc_1800A70F2
0x1800a70da  call    cs:__imp_GetLastError
0x1800a70e0  mov     [rbx+74h], eax
0x1800a70e3  mov     edi, eax
0x1800a70e5  test    eax, eax
0x1800a70e7  jle     short loc_1800A70F2
0x1800a70e9  movzx   edi, ax
0x1800a70ec  or      edi, 80070000h
0x1800a70f2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800a70f6  call    cs:__imp_LeaveCriticalSection
0x1800a70fc  mov     eax, edi
0x1800a70fe  add     rsp, 28h
0x1800a7102  pop     r15
0x1800a7104  pop     r14
0x1800a7106  pop     rdi
0x1800a7107  pop     rsi
0x1800a7108  pop     rbp
0x1800a7109  pop     rbx
0x1800a710a  retn
```
