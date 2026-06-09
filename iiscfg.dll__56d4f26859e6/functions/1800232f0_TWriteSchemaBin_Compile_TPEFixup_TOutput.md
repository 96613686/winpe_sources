# TWriteSchemaBin::Compile(TPEFixup &,TOutput &)

- ea: `0x1800232f0`
- end: `0x1800234a5`
- name: `?Compile@TWriteSchemaBin@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z`
- size: `437`
- prototype: `void __fastcall(TWriteSchemaBin *__hidden this, struct TPEFixup *, struct TOutput *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015f34`

## callees

- `0x1800234ac`
- `0x180024ab8`
- `0x1800259a8`
- `0x180025a98`
- `0x180025b18`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TWriteSchemaBin::Compile(
        TWriteSchemaBin *this,
        struct TPEFixup *a2,
        void (***a3)(struct TOutput *, const wchar_t *, ...))
{
  void (***v3)(struct TOutput *, const wchar_t *, ...); // rbx
  TWriteSchemaBin *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rax
  struct _SECURITY_ATTRIBUTES v7; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v8[40]; // [rsp+48h] [rbp-28h] BYREF
  int v9; // [rsp+80h] [rbp+10h] BYREF

  v3 = a3;
  v4 = this;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 5) = a3;
  TFixedTableHeapBuilder::BuildMetaTableHeap(this);
  memset(&v7, 0, sizeof(v7));
  TWriteSchemaBin::SetSecurityDescriptor(v4);
  v7.nLength = 24;
  v7.lpSecurityDescriptor = (LPVOID)*((_QWORD *)v4 + 7);
  TFile::TFile((TFile *)v8, *((const unsigned __int16 **)v4 + 10), v3, v5, &v7);
  LOBYTE(v9) = 22;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = -32;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = 123;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = 32;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = -122;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = 32;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = 24;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  LOBYTE(v9) = -32;
  TFile::Write((TFile *)v8, (const char *)&v9, 1u);
  v9 = 44793556;
  TFile::Write((TFile *)v8, (const char *)&v9, 4u);
  v9 = 269;
  TFile::Write((TFile *)v8, (const char *)&v9, 4u);
  v4 = (TWriteSchemaBin *)((char *)v4 + 8);
  v9 = (*(__int64 (__fastcall **)(TWriteSchemaBin *))(*(_QWORD *)v4 + 16LL))(v4);
  TFile::Write((TFile *)v8, (const char *)&v9, 4u);
  LODWORD(v3) = (*(__int64 (__fastcall **)(TWriteSchemaBin *))(*(_QWORD *)v4 + 16LL))(v4) - 20;
  v6 = (*(__int64 (__fastcall **)(TWriteSchemaBin *))(*(_QWORD *)v4 + 32LL))(v4);
  TFile::Write((TFile *)v8, (const char *)(v6 + 20), (DWORD)v3);
  TFile::~TFile((TFile *)v8);
}

```

## disassembly

```asm
0x1800232f0  mov     [rsp-8+arg_8], rbx
0x1800232f5  mov     [rsp-8+arg_10], rdi
0x1800232fa  push    rbp
0x1800232fb  mov     rbp, rsp
0x1800232fe  sub     rsp, 70h
0x180023302  mov     rbx, r8
0x180023305  mov     rdi, rcx
0x180023308  mov     [rcx+20h], rdx
0x18002330c  mov     [rcx+28h], rbx
0x180023310  call    ?BuildMetaTableHeap@TFixedTableHeapBuilder@@IEAAXXZ; TFixedTableHeapBuilder::BuildMetaTableHeap(void)
0x180023315  xorps   xmm0, xmm0
0x180023318  xor     eax, eax
0x18002331a  movups  xmmword ptr [rbp+var_40.nLength], xmm0
0x18002331e  mov     qword ptr [rbp+var_40.bInheritHandle], rax
0x180023322  mov     rcx, rdi; this
0x180023325  call    ?SetSecurityDescriptor@TWriteSchemaBin@@AEAAXXZ; TWriteSchemaBin::SetSecurityDescriptor(void)
0x18002332a  mov     [rbp+var_40.nLength], 18h
0x180023331  mov     rax, [rdi+38h]
0x180023335  mov     [rbp+var_40.lpSecurityDescriptor], rax
0x180023339  mov     [rbp+var_40.bInheritHandle], 0
0x180023340  lea     rax, [rbp+var_40]
0x180023344  mov     [rsp+70h+var_50], rax; struct _SECURITY_ATTRIBUTES *
0x180023349  mov     r8, rbx; struct TOutput *
0x18002334c  mov     rdx, [rdi+50h]; unsigned __int16 *
0x180023350  lea     rcx, [rbp+var_28]; this
0x180023354  call    ??0TFile@@QEAA@PEBGAEAVTOutput@@_NPEAU_SECURITY_ATTRIBUTES@@@Z; TFile::TFile(ushort const *,TOutput &,bool,_SECURITY_ATTRIBUTES *)
0x180023359  nop
0x18002335a  mov     byte ptr [rbp+arg_0], 16h
0x18002335e  mov     ebx, 1
0x180023363  mov     r8d, ebx; unsigned int
0x180023366  lea     rdx, [rbp+arg_0]; char *
0x18002336a  lea     rcx, [rbp+var_28]; this
0x18002336e  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x180023373  mov     byte ptr [rbp+arg_0], 0E0h
0x180023377  mov     r8d, ebx; unsigned int
0x18002337a  lea     rdx, [rbp+arg_0]; char *
0x18002337e  lea     rcx, [rbp+var_28]; this
0x180023382  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x180023387  mov     byte ptr [rbp+arg_0], 7Bh ; '{'
0x18002338b  mov     r8d, ebx; unsigned int
0x18002338e  lea     rdx, [rbp+arg_0]; char *
0x180023392  lea     rcx, [rbp+var_28]; this
0x180023396  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x18002339b  mov     byte ptr [rbp+arg_0], 20h ; ' '
0x18002339f  mov     r8d, ebx; unsigned int
0x1800233a2  lea     rdx, [rbp+arg_0]; char *
0x1800233a6  lea     rcx, [rbp+var_28]; this
0x1800233aa  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x1800233af  mov     byte ptr [rbp+arg_0], 86h
0x1800233b3  mov     r8d, ebx; unsigned int
0x1800233b6  lea     rdx, [rbp+arg_0]; char *
0x1800233ba  lea     rcx, [rbp+var_28]; this
0x1800233be  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x1800233c3  mov     byte ptr [rbp+arg_0], 20h ; ' '
0x1800233c7  mov     r8d, ebx; unsigned int
0x1800233ca  lea     rdx, [rbp+arg_0]; char *
0x1800233ce  lea     rcx, [rbp+var_28]; this
0x1800233d2  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x1800233d7  mov     byte ptr [rbp+arg_0], 18h
0x1800233db  mov     r8d, ebx; unsigned int
0x1800233de  lea     rdx, [rbp+arg_0]; char *
0x1800233e2  lea     rcx, [rbp+var_28]; this
0x1800233e6  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x1800233eb  mov     byte ptr [rbp+arg_0], 0E0h
0x1800233ef  mov     r8d, ebx; unsigned int
0x1800233f2  lea     rdx, [rbp+arg_0]; char *
0x1800233f6  lea     rcx, [rbp+var_28]; this
0x1800233fa  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x1800233ff  mov     [rbp+arg_0], 2AB7ED4h
0x180023406  mov     ebx, 4
0x18002340b  mov     r8d, ebx; unsigned int
0x18002340e  lea     rdx, [rbp+arg_0]; char *
0x180023412  lea     rcx, [rbp+var_28]; this
0x180023416  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x18002341b  mov     [rbp+arg_0], 10Dh
0x180023422  mov     r8d, ebx; unsigned int
0x180023425  lea     rdx, [rbp+arg_0]; char *
0x180023429  lea     rcx, [rbp+var_28]; this
0x18002342d  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x180023432  add     rdi, 8
0x180023436  mov     rax, [rdi]
0x180023439  mov     rcx, rdi
0x18002343c  mov     rax, [rax+10h]
0x180023440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023445  mov     [rbp+arg_0], eax
0x180023448  mov     r8d, ebx; unsigned int
0x18002344b  lea     rdx, [rbp+arg_0]; char *
0x18002344f  lea     rcx, [rbp+var_28]; this
0x180023453  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x180023458  mov     rax, [rdi]
0x18002345b  mov     rcx, rdi
0x18002345e  mov     rax, [rax+10h]
0x180023462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023467  lea     ebx, [rax-14h]
0x18002346a  mov     rax, [rdi]
0x18002346d  mov     rcx, rdi
0x180023470  mov     rax, [rax+20h]
0x180023474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023479  lea     rdx, [rax+14h]; char *
0x18002347d  mov     r8d, ebx; unsigned int
0x180023480  lea     rcx, [rbp+var_28]; this
0x180023484  call    ?Write@TFile@@QEBAXPEBDI@Z; TFile::Write(char const *,uint)
0x180023489  nop
0x18002348a  lea     rcx, [rbp+var_28]; this
0x18002348e  call    ??1TFile@@UEAA@XZ; TFile::~TFile(void)
0x180023493  lea     r11, [rsp+70h+var_s0]
0x180023498  mov     rbx, [r11+18h]
0x18002349c  mov     rdi, [r11+20h]
0x1800234a0  mov     rsp, r11
0x1800234a3  pop     rbp
0x1800234a4  retn
```
