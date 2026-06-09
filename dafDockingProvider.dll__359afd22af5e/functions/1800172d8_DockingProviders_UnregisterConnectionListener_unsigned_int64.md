# DockingProviders::UnregisterConnectionListener(unsigned __int64)

- ea: `0x1800172d8`
- end: `0x18001736c`
- name: `?UnregisterConnectionListener@DockingProviders@@QEAAJ_K@Z`
- size: `148`
- prototype: `__int64 __fastcall(DockingProviders *this, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001134c`
- `0x18001c330`

## callees

- `0x1800014d0`
- `0x180015ca8`
- `0x1800170b0`
- `0x1800172d8`
- `0x180017798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001735a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001735a`

## pseudocode

```c
__int64 __fastcall DockingProviders::UnregisterConnectionListener(DockingProviders *this, void **a2)
{
  int IsRegistrationValid; // eax
  __int64 v5; // r8
  unsigned int v7; // ebx

  IsRegistrationValid = ListenerRegistration::IsRegistrationValid((unsigned __int64)a2);
  if ( IsRegistrationValid < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Id(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v5, a2, IsRegistrationValid);
    }
    return 2147943568LL;
  }
  if ( !a2 )
    return 2147943568LL;
  v7 = ListenerRegistration::Unregister(
         (ListenerRegistration *)a2,
         *((_DWORD *)this + 4),
         *((struct DockingProvider ***)this + 3));
  operator delete(a2[8]);
  DeleteCriticalSection((LPCRITICAL_SECTION)a2);
  operator delete(a2);
  return v7;
}

```

## disassembly

```asm
0x1800172d8  mov     [rsp+arg_0], rbx
0x1800172dd  push    rdi
0x1800172de  sub     rsp, 30h
0x1800172e2  mov     rdi, rdx
0x1800172e5  mov     rbx, rcx
0x1800172e8  mov     rcx, rdx; unsigned __int64
0x1800172eb  call    ?IsRegistrationValid@ListenerRegistration@@SAJ_K@Z; ListenerRegistration::IsRegistrationValid(unsigned __int64)
0x1800172f0  test    eax, eax
0x1800172f2  jns     short loc_180017333
0x1800172f4  lea     rdx, WPP_GLOBAL_Control
0x1800172fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017302  cmp     rcx, rdx
0x180017305  jz      short loc_180017323
0x180017307  cmp     byte ptr [rcx+19h], 1
0x18001730b  jb      short loc_180017323
0x18001730d  test    byte ptr [rcx+1Ch], 1
0x180017311  jz      short loc_180017323
0x180017313  mov     [rsp+38h+var_18], eax
0x180017317  mov     r9, rdi
0x18001731a  mov     rcx, [rcx+10h]
0x18001731e  call    WPP_SF_Id
0x180017323  mov     eax, 80070490h
0x180017328  mov     rbx, [rsp+38h+arg_0]
0x18001732d  add     rsp, 30h
0x180017331  pop     rdi
0x180017332  retn
0x180017333  test    rdi, rdi
0x180017336  jz      short loc_180017323
0x180017338  mov     [rsp+38h+arg_10], rdi
0x18001733d  mov     r8, [rbx+18h]; struct DockingProvider **
0x180017341  mov     edx, [rbx+10h]; unsigned int
0x180017344  mov     rcx, rdi; this
0x180017347  call    ?Unregister@ListenerRegistration@@QEAAJIPEAPEAVDockingProvider@@@Z; ListenerRegistration::Unregister(uint,DockingProvider * *)
0x18001734c  mov     ebx, eax
0x18001734e  mov     rcx, [rdi+40h]; Block
0x180017352  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017357  mov     rcx, rdi; lpCriticalSection
0x18001735a  call    cs:__imp_DeleteCriticalSection
0x180017360  mov     rcx, rdi; Block
0x180017363  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180017368  mov     eax, ebx
0x18001736a  jmp     short loc_180017328
```
