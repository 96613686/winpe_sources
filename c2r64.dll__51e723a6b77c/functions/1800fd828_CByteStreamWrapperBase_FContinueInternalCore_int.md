# CByteStreamWrapperBase::FContinueInternalCore(int)

- ea: `0x1800fd828`
- end: `0x1800fd8f8`
- name: `?FContinueInternalCore@CByteStreamWrapperBase@@AEAAHH@Z`
- size: `208`
- prototype: `__int64 __fastcall(CByteStreamWrapperBase *__hidden this, int)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x1800fd470`
- `0x1800fd570`
- `0x1800fd810`
- `0x1800fd9fc`
- `0x1800fdaf8`
- `0x1800fde50`
- `0x1800fdfe0`
- `0x1800fe118`
- `0x1800fe3dc`
- `0x1800fe580`

## callees

- `0x180012bf8`
- `0x1800fd828`
- `0x1801054d0`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1800fd8ae`
- `KERNEL32!GetTickCount64` at `0x1800fd8d9`
- `KERNEL32!GetTickCount64` at `0x1800fd8ae`
- `KERNEL32!GetTickCount64` at `0x1800fd8d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800fd83c`
- `KERNEL32!GetCurrentThreadId` at `0x1800fd83c`

## pseudocode

```c
__int64 __fastcall CByteStreamWrapperBase::FContinueInternalCore(CByteStreamWrapperBase *this, int a2)
{
  DWORD CurrentThreadId; // edi
  __int64 v5; // rax
  unsigned __int64 v6; // rax
  __int64 result; // rax
  int v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  if ( *((_DWORD *)this + 20) == CurrentThreadId || !*((_DWORD *)this + 20) )
  {
    v9 = 0;
    v5 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 40);
    (*(void (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v5 + 56LL))(v5, &v9);
    if ( v9 )
    {
      v6 = 100LL * *((_QWORD *)this + 8) / v9;
      if ( v6 > 0x64 )
        LODWORD(v6) = 100;
      *((_DWORD *)this + 21) = v6;
    }
    else
    {
      *((_DWORD *)this + 21) = 0;
    }
  }
  if ( *((_DWORD *)this + 19) == CurrentThreadId && (!a2 || GetTickCount64() - *((_QWORD *)this + 11) >= 0xFA) )
  {
    v8 = *((_DWORD *)this + 21);
    result = CallFContinue(*((struct IMetroProgress **)this + 6), (const struct ContinueEventArgs *)&v8);
    if ( !(_DWORD)result )
      return result;
    *((_QWORD *)this + 11) = GetTickCount64();
  }
  return 1;
}

```

## disassembly

```asm
0x1800fd828  mov     [rsp+arg_8], rbx
0x1800fd82d  mov     [rsp+arg_18], rsi
0x1800fd832  push    rdi
0x1800fd833  sub     rsp, 20h
0x1800fd837  mov     esi, edx
0x1800fd839  mov     rbx, rcx
0x1800fd83c  call    cs:__imp_GetCurrentThreadId
0x1800fd842  mov     edi, eax
0x1800fd844  cmp     [rbx+50h], eax
0x1800fd847  jz      short loc_1800FD84F
0x1800fd849  cmp     dword ptr [rbx+50h], 0
0x1800fd84d  jnz     short loc_1800FD8A5
0x1800fd84f  mov     [rsp+28h+arg_10], 0
0x1800fd858  lea     rcx, [rbx+28h]
0x1800fd85c  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800fd861  mov     r8, rax
0x1800fd864  mov     rcx, [rax]
0x1800fd867  mov     rax, [rcx+38h]
0x1800fd86b  lea     rdx, [rsp+28h+arg_10]
0x1800fd870  mov     rcx, r8
0x1800fd873  call    cs:__guard_dispatch_icall_fptr
0x1800fd879  mov     rcx, [rsp+28h+arg_10]
0x1800fd87e  test    rcx, rcx
0x1800fd881  jz      short loc_1800FD89E
0x1800fd883  imul    rax, [rbx+40h], 64h ; 'd'
0x1800fd888  xor     edx, edx
0x1800fd88a  div     rcx
0x1800fd88d  mov     ecx, 64h ; 'd'
0x1800fd892  cmp     rax, rcx
0x1800fd895  cmova   rax, rcx
0x1800fd899  mov     [rbx+54h], eax
0x1800fd89c  jmp     short loc_1800FD8A5
0x1800fd89e  mov     dword ptr [rbx+54h], 0
0x1800fd8a5  cmp     [rbx+4Ch], edi
0x1800fd8a8  jnz     short loc_1800FD8E3
0x1800fd8aa  test    esi, esi
0x1800fd8ac  jz      short loc_1800FD8C0
0x1800fd8ae  call    cs:__imp_GetTickCount64
0x1800fd8b4  sub     rax, [rbx+58h]
0x1800fd8b8  cmp     rax, 0FAh
0x1800fd8be  jb      short loc_1800FD8E3
0x1800fd8c0  mov     eax, [rbx+54h]
0x1800fd8c3  mov     [rsp+28h+arg_0], eax
0x1800fd8c7  lea     rdx, [rsp+28h+arg_0]; struct ContinueEventArgs *
0x1800fd8cc  mov     rcx, [rbx+30h]; struct IMetroProgress *
0x1800fd8d0  call    ?CallFContinue@@YAHPEAUIMetroProgress@@PEBUContinueEventArgs@@@Z; CallFContinue(IMetroProgress *,ContinueEventArgs const *)
0x1800fd8d5  test    eax, eax
0x1800fd8d7  jz      short loc_1800FD8E8
0x1800fd8d9  call    cs:__imp_GetTickCount64
0x1800fd8df  mov     [rbx+58h], rax
0x1800fd8e3  mov     eax, 1
0x1800fd8e8  mov     rbx, [rsp+28h+arg_8]
0x1800fd8ed  mov     rsi, [rsp+28h+arg_18]
0x1800fd8f2  add     rsp, 20h
0x1800fd8f6  pop     rdi
0x1800fd8f7  retn
```
