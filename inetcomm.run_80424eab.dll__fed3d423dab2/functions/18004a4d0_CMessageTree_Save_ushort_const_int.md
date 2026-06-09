# CMessageTree::Save(ushort const *,int)

- ea: `0x18004a4d0`
- end: `0x18004a620`
- name: `?Save@CMessageTree@@UEAAJPEBGH@Z`
- size: `336`
- prototype: `__int64 __fastcall(CMessageTree *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005748`
- `0x18004a4d0`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrCopyStream` at `0x18004a580`
- `MSOERT2!HrCopyStream` at `0x18004a580`
- `MSOERT2!PszDupW` at `0x18004a5d6`
- `MSOERT2!PszDupW` at `0x18004a5d6`
- `MSOERT2!OpenFileStreamW` at `0x18004a52e`
- `MSOERT2!OpenFileStreamW` at `0x18004a52e`
- `KERNEL32!LeaveCriticalSection` at `0x18004a605`
- `KERNEL32!LeaveCriticalSection` at `0x18004a605`
- `KERNEL32!EnterCriticalSection` at `0x18004a515`
- `KERNEL32!EnterCriticalSection` at `0x18004a515`

## pseudocode

```c
__int64 __fastcall CMessageTree::Save(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // r14
  int v8; // ebx
  char *p_LockSemaphore; // rcx
  __int64 (__fastcall **LockSemaphore)(char *, _QWORD, __int64); // rax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF
  __int64 v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  v14 = 0;
  if ( !a2 )
    return 2147942487LL;
  v7 = this + 9;
  EnterCriticalSection(this + 9);
  v8 = OpenFileStreamW(a2, 2, 3221225472LL, &v13);
  if ( v8 >= 0 )
  {
    p_LockSemaphore = (char *)&this[-1].LockSemaphore;
    LockSemaphore = (__int64 (__fastcall **)(char *, _QWORD, __int64))this[-1].LockSemaphore;
    if ( a3 )
    {
      v11 = LockSemaphore[6](p_LockSemaphore, v13, 1);
LABEL_8:
      v8 = v11;
      if ( v11 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, 0);
        if ( v8 >= 0 )
        {
          if ( a3 )
          {
            if ( this[3].OwningThread )
            {
              ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
              this[3].OwningThread = 0;
            }
            v12 = PszDupW(a2);
            this[3].OwningThread = (HANDLE)v12;
            if ( !v12 )
              v8 = -2147024882;
          }
        }
      }
      goto LABEL_15;
    }
    v8 = ((__int64 (__fastcall **)(char *, __int64 *, __int64))LockSemaphore)[9](p_LockSemaphore, &v14, 1);
    if ( v8 >= 0 )
    {
      v11 = HrCopyStream(v14, v13, 0);
      goto LABEL_8;
    }
  }
LABEL_15:
  OE_SafeReleaseAndNullPtr<IStream>(&v13);
  OE_SafeReleaseAndNullPtr<IStream>(&v14);
  LeaveCriticalSection(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004a4d0  mov     rax, rsp
0x18004a4d3  mov     [rax+8], rbx
0x18004a4d7  mov     [rax+18h], rbp
0x18004a4db  push    rsi
0x18004a4dc  push    rdi
0x18004a4dd  push    r14
0x18004a4df  sub     rsp, 20h
0x18004a4e3  mov     qword ptr [rax+10h], 0
0x18004a4eb  mov     ebp, r8d
0x18004a4ee  mov     qword ptr [rax+20h], 0
0x18004a4f6  mov     rsi, rdx
0x18004a4f9  mov     rdi, rcx
0x18004a4fc  test    rdx, rdx
0x18004a4ff  jnz     short loc_18004A50B
0x18004a501  mov     eax, 80070057h
0x18004a506  jmp     loc_18004A60D
0x18004a50b  lea     r14, [rcx+168h]
0x18004a512  mov     rcx, r14; lpCriticalSection
0x18004a515  call    cs:__imp_EnterCriticalSection
0x18004a51b  lea     r9, [rsp+38h+arg_8]
0x18004a520  mov     edx, 2
0x18004a525  mov     r8d, 0C0000000h
0x18004a52b  mov     rcx, rsi
0x18004a52e  call    cs:__imp_OpenFileStreamW
0x18004a534  mov     ebx, eax
0x18004a536  test    eax, eax
0x18004a538  js      loc_18004A5EE
0x18004a53e  lea     rcx, [rdi-10h]
0x18004a542  mov     r8d, 1
0x18004a548  mov     rax, [rcx]
0x18004a54b  test    ebp, ebp
0x18004a54d  jz      short loc_18004A55F
0x18004a54f  mov     rdx, [rsp+38h+arg_8]
0x18004a554  mov     rax, [rax+30h]
0x18004a558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a55d  jmp     short loc_18004A586
0x18004a55f  mov     rax, [rax+48h]
0x18004a563  lea     rdx, [rsp+38h+arg_18]
0x18004a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a56d  mov     ebx, eax
0x18004a56f  test    eax, eax
0x18004a571  js      short loc_18004A5EE
0x18004a573  mov     rdx, [rsp+38h+arg_8]
0x18004a578  xor     r8d, r8d
0x18004a57b  mov     rcx, [rsp+38h+arg_18]
0x18004a580  call    cs:__imp_HrCopyStream
0x18004a586  mov     ebx, eax
0x18004a588  test    eax, eax
0x18004a58a  js      short loc_18004A5EE
0x18004a58c  mov     rcx, [rsp+38h+arg_8]
0x18004a591  xor     edx, edx
0x18004a593  mov     rax, [rcx]
0x18004a596  mov     rax, [rax+40h]
0x18004a59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a59f  mov     ebx, eax
0x18004a5a1  test    eax, eax
0x18004a5a3  js      short loc_18004A5EE
0x18004a5a5  test    ebp, ebp
0x18004a5a7  jz      short loc_18004A5EE
0x18004a5a9  mov     rdx, [rdi+88h]
0x18004a5b0  test    rdx, rdx
0x18004a5b3  jz      short loc_18004A5D3
0x18004a5b5  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18004a5bc  mov     rax, [rcx]
0x18004a5bf  mov     rax, [rax+28h]
0x18004a5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5c8  mov     qword ptr [rdi+88h], 0
0x18004a5d3  mov     rcx, rsi
0x18004a5d6  call    cs:__imp_PszDupW
0x18004a5dc  test    rax, rax
0x18004a5df  mov     [rdi+88h], rax
0x18004a5e6  mov     ecx, 8007000Eh
0x18004a5eb  cmovz   ebx, ecx
0x18004a5ee  lea     rcx, [rsp+38h+arg_8]
0x18004a5f3  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18004a5f8  lea     rcx, [rsp+38h+arg_18]
0x18004a5fd  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18004a602  mov     rcx, r14; lpCriticalSection
0x18004a605  call    cs:__imp_LeaveCriticalSection
0x18004a60b  mov     eax, ebx
0x18004a60d  mov     rbx, [rsp+38h+arg_0]
0x18004a612  mov     rbp, [rsp+38h+arg_10]
0x18004a617  add     rsp, 20h
0x18004a61b  pop     r14
0x18004a61d  pop     rdi
0x18004a61e  pop     rsi
0x18004a61f  retn
```
