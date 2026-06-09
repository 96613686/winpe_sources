# ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::Release(void)

- ea: `0x180039250`
- end: `0x1800392b0`
- name: `?Release@?$CComObject@VCMsftDiscFormat2TrackAtOnce@@@ATL@@UEAAKXZ`
- size: `96`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800392c0`
- `0x1800392d0`
- `0x1800392e0`
- `0x1800392f0`
- `0x180039300`
- `0x180039310`

## callees

- `0x18000cbf4`
- `0x18000ea44`
- `0x180039250`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMsftDiscFormat2TrackAtOnce>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 28);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 304LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180039250  mov     [rsp+arg_8], rbx
0x180039255  push    rdi
0x180039256  sub     rsp, 20h
0x18003925a  mov     rbx, rcx
0x18003925d  add     rcx, 70h ; 'p'; volatile int *
0x180039261  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180039266  mov     edi, eax
0x180039268  test    eax, eax
0x18003926a  jnz     short loc_1800392A3
0x18003926c  lea     rcx, [rsp+28h+arg_0]; this
0x180039271  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180039276  test    rbx, rbx
0x180039279  jz      short loc_180039290
0x18003927b  mov     rdx, [rbx]
0x18003927e  mov     rcx, rbx
0x180039281  mov     rax, [rdx+130h]
0x180039288  lea     edx, [rdi+1]
0x18003928b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039290  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180039297  mov     rax, [rcx]
0x18003929a  mov     rax, [rax+10h]
0x18003929e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392a3  mov     rbx, [rsp+28h+arg_8]
0x1800392a8  mov     eax, edi
0x1800392aa  add     rsp, 20h
0x1800392ae  pop     rdi
0x1800392af  retn
```
