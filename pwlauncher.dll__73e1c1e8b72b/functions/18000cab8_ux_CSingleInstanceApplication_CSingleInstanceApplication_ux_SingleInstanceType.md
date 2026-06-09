# ux::CSingleInstanceApplication::CSingleInstanceApplication(ux::SingleInstanceType)

- ea: `0x18000cab8`
- end: `0x18000cb66`
- name: `??0CSingleInstanceApplication@ux@@QEAA@W4SingleInstanceType@1@@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008e20`

## callees

- `0x180009c58`
- `0x18000cab8`
- `0x180011010`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18000cb11`
- `KERNEL32!CreateMutexW` at `0x18000cb11`
- `KERNEL32!GetLastError` at `0x18000cb1b`
- `KERNEL32!GetLastError` at `0x18000cb1b`

## pseudocode

```c
__int64 __fastcall ux::CSingleInstanceApplication::CSingleInstanceApplication(__int64 a1)
{
  _QWORD *v2; // rbx
  char v3; // si
  DWORD LastError; // eax

  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = &ux::CSingleInstanceApplication::`vftable';
  v2 = (_QWORD *)ATL::CSimpleStringT<unsigned short,0>::CloneData(ux::CSingleInstanceApplication::PER_MACHINE_MUTEX_NAME - 24);
  v3 = 1;
  *(_QWORD *)(a1 + 16) = &CMutex::`vftable';
  *(_QWORD *)(a1 + 24) = CreateMutexW(
                           0,
                           1,
                           (LPCWSTR)((unsigned __int64)(v2 + 3) & -(__int64)(*((_DWORD *)v2 + 2) != 0)));
  LastError = GetLastError();
  if ( LastError == 183 || LastError == 5 )
    v3 = 0;
  *(_BYTE *)(a1 + 12) = v3;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v2 + 8LL))(*v2, v2);
  return a1;
}

```

## disassembly

```asm
0x18000cab8  mov     [rsp+arg_8], rbx
0x18000cabd  mov     [rsp+arg_10], rsi
0x18000cac2  push    rdi
0x18000cac3  sub     rsp, 20h
0x18000cac7  mov     rdi, rcx
0x18000caca  mov     dword ptr [rcx+8], 0
0x18000cad1  lea     rax, ??_7CSingleInstanceApplication@ux@@6B@; const ux::CSingleInstanceApplication::`vftable'
0x18000cad8  mov     [rcx], rax
0x18000cadb  mov     rcx, cs:?PER_MACHINE_MUTEX_NAME@CSingleInstanceApplication@ux@@0V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const ux::CSingleInstanceApplication::PER_MACHINE_MUTEX_NAME
0x18000cae2  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18000cae6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000caeb  mov     rbx, rax
0x18000caee  mov     esi, 1
0x18000caf3  lea     rdx, [rax+18h]
0x18000caf7  lea     rax, ??_7CMutex@@6B@; const CMutex::`vftable'
0x18000cafe  mov     [rdi+10h], rax
0x18000cb02  mov     ecx, [rdx-10h]
0x18000cb05  neg     ecx
0x18000cb07  sbb     r8, r8
0x18000cb0a  xor     ecx, ecx; lpMutexAttributes
0x18000cb0c  and     r8, rdx; lpName
0x18000cb0f  mov     edx, esi; bInitialOwner
0x18000cb11  call    cs:__imp_CreateMutexW
0x18000cb17  mov     [rdi+18h], rax
0x18000cb1b  call    cs:__imp_GetLastError
0x18000cb21  cmp     eax, 0B7h
0x18000cb26  jz      short loc_18000CB2D
0x18000cb28  cmp     eax, 5
0x18000cb2b  jnz     short loc_18000CB30
0x18000cb2d  xor     sil, sil
0x18000cb30  mov     [rdi+0Ch], sil
0x18000cb34  or      eax, 0FFFFFFFFh
0x18000cb37  lock xadd [rbx+10h], eax
0x18000cb3c  sub     eax, 1
0x18000cb3f  jg      short loc_18000CB53
0x18000cb41  mov     rcx, [rbx]
0x18000cb44  mov     rdx, rbx
0x18000cb47  mov     rax, [rcx]
0x18000cb4a  mov     rax, [rax+8]
0x18000cb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb53  mov     rbx, [rsp+28h+arg_8]
0x18000cb58  mov     rax, rdi
0x18000cb5b  mov     rsi, [rsp+28h+arg_10]
0x18000cb60  add     rsp, 20h
0x18000cb64  pop     rdi
0x18000cb65  retn
```
