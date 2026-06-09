# GuestStateFile::GuestStateFile(GuestStateAccessFormat)

- ea: `0x18005279c`
- end: `0x180052927`
- name: `??0GuestStateFile@@QEAA@W4GuestStateAccessFormat@@@Z`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180051988`

## callees

- `0x18004e3d0`
- `0x18005279c`
- `0x18005ae50`
- `0x18005b3c8`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180052824`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005285e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180052824`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005285e`
- `RPCRT4!UuidCreate` at `0x1800527eb`
- `RPCRT4!UuidCreate` at `0x1800527eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GuestStateFile::GuestStateFile(__int64 a1, int a2)
{
  __int64 *v4; // rax
  __int64 v5; // rbx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // [rsp+28h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]

  v10 = a1;
  *(_QWORD *)(a1 + 8) = &GuestStateFile::`vbtable';
  Vml::VmSharableObject::VmSharableObject((Vml::VmSharableObject *)(a1 + 224));
  *(_WORD *)(a1 + 16) = 10240;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(UUID *)(a1 + 20) = Uuid;
  *(_QWORD *)a1 = &GuestStateFile::`vftable'{for `IGuestStateFile'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &GuestStateFile::`vftable'{for `Vml::VmSharableObject'};
  *(_DWORD *)(a1 + 48) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 40));
  *(_QWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_WORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 96) = 0;
  *(_DWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 128) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 120));
  *(_QWORD *)(a1 + 136) = -1;
  *(_QWORD *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 152) = 0;
  *(_OWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 7;
  *(_WORD *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 216) = a2;
  *(_QWORD *)&Uuid.Data1 = 0;
  if ( (a2 & 1) != 0 )
    v4 = (__int64 *)GuestStateRawData::CreateInstance(&v8);
  else
    v4 = (__int64 *)GuestStateData::CreateInstance(&v8);
  v5 = *v4;
  *v4 = 0;
  if ( v8 )
    (**v8)(v8, 1);
  v6 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 56);
  *(_QWORD *)(a1 + 56) = v5;
  if ( v6 )
    (**v6)(v6, 1);
  return a1;
}

```

## disassembly

```asm
0x18005279c  mov     [rsp+arg_8], rbx
0x1800527a1  push    rdi
0x1800527a2  sub     rsp, 50h
0x1800527a6  mov     ebx, edx
0x1800527a8  mov     rdi, rcx
0x1800527ab  mov     [rsp+58h+var_18], rcx
0x1800527b0  mov     [rsp+58h+var_38], 0
0x1800527b8  lea     rax, ??_8GuestStateFile@@7B@; const GuestStateFile::`vbtable'
0x1800527bf  mov     [rcx+8], rax
0x1800527c3  add     rcx, 0E0h; this
0x1800527ca  call    ??0VmSharableObject@Vml@@IEAA@XZ; Vml::VmSharableObject::VmSharableObject(void)
0x1800527cf  nop
0x1800527d0  mov     [rsp+58h+var_38], 1
0x1800527d8  mov     word ptr [rdi+10h], 2800h
0x1800527de  xorps   xmm0, xmm0
0x1800527e1  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x1800527e6  lea     rcx, [rsp+58h+Uuid]; Uuid
0x1800527eb  call    cs:__imp_UuidCreate
0x1800527f1  movups  xmm0, xmmword ptr [rsp+58h+Uuid.Data1]
0x1800527f6  movdqu  xmmword ptr [rdi+14h], xmm0
0x1800527fb  lea     rax, ??_7GuestStateFile@@6BIGuestStateFile@@@; const GuestStateFile::`vftable'{for `IGuestStateFile'}
0x180052802  mov     [rdi], rax
0x180052805  mov     rax, [rdi+8]
0x180052809  movsxd  rcx, dword ptr [rax+4]
0x18005280d  lea     rax, ??_7GuestStateFile@@6BVmSharableObject@Vml@@@; const GuestStateFile::`vftable'{for `Vml::VmSharableObject'}
0x180052814  mov     [rcx+rdi+8], rax
0x180052819  lea     rcx, [rdi+28h]; SRWLock
0x18005281d  mov     dword ptr [rcx+8], 0
0x180052824  call    cs:__imp_InitializeSRWLock
0x18005282a  mov     qword ptr [rdi+38h], 0
0x180052832  xorps   xmm0, xmm0
0x180052835  movups  xmmword ptr [rdi+40h], xmm0
0x180052839  mov     qword ptr [rdi+50h], 0
0x180052841  mov     qword ptr [rdi+58h], 7
0x180052849  xor     eax, eax
0x18005284b  mov     [rdi+40h], ax
0x18005284f  movdqu  xmmword ptr [rdi+60h], xmm0
0x180052854  mov     [rdi+70h], eax
0x180052857  lea     rcx, [rdi+78h]; SRWLock
0x18005285b  mov     [rcx+8], eax
0x18005285e  call    cs:__imp_InitializeSRWLock
0x180052864  mov     qword ptr [rdi+88h], 0FFFFFFFFFFFFFFFFh
0x18005286f  mov     qword ptr [rdi+90h], 0
0x18005287a  xorps   xmm0, xmm0
0x18005287d  movups  xmmword ptr [rdi+98h], xmm0
0x180052884  movups  xmmword ptr [rdi+0A8h], xmm0
0x18005288b  xorps   xmm1, xmm1
0x18005288e  movups  xmmword ptr [rdi+0B8h], xmm1
0x180052895  mov     qword ptr [rdi+0C8h], 0
0x1800528a0  mov     qword ptr [rdi+0D0h], 7
0x1800528ab  xor     eax, eax
0x1800528ad  mov     [rdi+0B8h], ax
0x1800528b4  mov     [rdi+0D8h], ebx
0x1800528ba  mov     qword ptr [rsp+58h+Uuid.Data1], rax
0x1800528bf  lea     rcx, [rsp+58h+var_30]
0x1800528c4  test    bl, 1
0x1800528c7  jz      short loc_1800528D2
0x1800528c9  mov     edx, ebx
0x1800528cb  call    ?CreateInstance@GuestStateRawData@@SA?AV?$unique_ptr@VIGuestStateData@@U?$default_delete@VIGuestStateData@@@std@@@std@@W4GuestStateAccessFormat@@@Z; GuestStateRawData::CreateInstance(GuestStateAccessFormat)
0x1800528d0  jmp     short loc_1800528D7
0x1800528d2  call    ?CreateInstance@GuestStateData@@SA?AV?$unique_ptr@VIGuestStateData@@U?$default_delete@VIGuestStateData@@@std@@@std@@XZ; GuestStateData::CreateInstance(void)
0x1800528d7  mov     rbx, [rax]
0x1800528da  mov     qword ptr [rax], 0
0x1800528e1  mov     rcx, [rsp+58h+var_30]
0x1800528e6  test    rcx, rcx
0x1800528e9  jz      short loc_1800528FB
0x1800528eb  mov     rax, [rcx]
0x1800528ee  mov     edx, 1
0x1800528f3  mov     rax, [rax]
0x1800528f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528fb  mov     rcx, [rdi+38h]
0x1800528ff  mov     [rdi+38h], rbx
0x180052903  test    rcx, rcx
0x180052906  jz      short loc_180052919
0x180052908  mov     r8, [rcx]
0x18005290b  mov     edx, 1
0x180052910  mov     rax, [r8]
0x180052913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052918  nop
0x180052919  mov     rax, rdi
0x18005291c  mov     rbx, [rsp+58h+arg_8]
0x180052921  add     rsp, 50h
0x180052925  pop     rdi
0x180052926  retn
```
