# CDirectMusic::CreatePort(_GUID const &,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *,IUnknown *)

- ea: `0x1800131a0`
- end: `0x180013409`
- name: `?CreatePort@CDirectMusic@@UEAAJAEBU_GUID@@PEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@PEAUIUnknown@@@Z`
- size: `617`
- prototype: `__int64 __usercall@<rax>(CDirectMusic *__hidden this@<rcx>, const struct _GUID *@<rdx>, struct _DMUS_PORTPARAMS8 *@<r8>, struct IDirectMusicPort **@<r9>, struct IUnknown *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1800111fc`
- `0x1800131a0`
- `0x180013654`
- `0x180013ed4`
- `0x18001ae48`
- `0x18001e008`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusic::CreatePort(
        CDirectMusic *this,
        const struct _GUID *a2,
        struct _DMUS_PORTPARAMS8 *a3,
        struct IDirectMusicPort **a4,
        struct IUnknown *a5)
{
  unsigned int v9; // r15d
  bool v10; // zf
  __int64 v11; // rax
  __int64 v12; // rbx
  HRESULT CDirectMusicEmulatePort; // eax
  unsigned int v14; // esi
  struct IDirectMusicPort *v15; // rcx
  int v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h] BYREF
  struct _GUID v18; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+60h] [rbp-10h]
  int v20; // [rsp+64h] [rbp-Ch]
  int v21; // [rsp+B8h] [rbp+48h] BYREF

  if ( !a4 )
    return 2147500035LL;
  if ( a5 )
    return 2147746064LL;
  if ( !a2 )
    return 2147500035LL;
  if ( !a3 )
    return 2147942487LL;
  if ( a3->dwSize == 32 )
  {
    v9 = 7;
  }
  else if ( a3->dwSize == 36 )
  {
    v9 = 8;
  }
  else
  {
    v9 = 7;
    if ( a3->dwSize <= 0x20 )
      return 2147942487LL;
  }
  v10 = *((_DWORD *)this + 26) == 0;
  v18 = 0;
  if ( v10 )
    return 2289570105LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
  {
    CDirectMusic::GetDefaultPortI(this, &v18);
  }
  else
  {
    v18 = *a2;
  }
  *a4 = 0;
  if ( !(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 40LL))((char *)this + 32) )
    CDirectMusic::UpdatePortList(this);
  v11 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 40LL))((char *)this + 32);
  if ( !v11 )
    return 2147500034LL;
  while ( 1 )
  {
    v12 = *(_QWORD *)(v11 + 16);
    if ( *(_QWORD *)(v12 + 40) == *(_QWORD *)&v18.Data1 && *(_QWORD *)(v12 + 48) == *(_QWORD *)v18.Data4 )
      break;
    v11 = *(_QWORD *)(v11 + 8);
    if ( !v11 )
      return 2147500034LL;
  }
  if ( !v12 )
    return 2147500034LL;
  if ( *(_DWORD *)v12 == 1 )
  {
    CDirectMusicEmulatePort = CreateCDirectMusicEmulatePort(*(struct tagPORTENTRY **)(v11 + 16), this, a3, a4);
    goto LABEL_32;
  }
  if ( *(_DWORD *)v12 == 2 )
  {
    CDirectMusicEmulatePort = CreateCDirectMusicSynthPort((struct tagPORTENTRY *)v12, this, v9, a3, a4);
    goto LABEL_32;
  }
  if ( *(_DWORD *)v12 != 3 )
    return 2147500034LL;
  CDirectMusicEmulatePort = CreateCDirectMusicUMAPort(*(struct tagPORTENTRY **)(v11 + 16), this, a3, a4);
LABEL_32:
  v14 = CDirectMusicEmulatePort;
  if ( CDirectMusicEmulatePort >= 0 )
  {
    if ( *(_DWORD *)v12 != 2 && v9 >= 8 && SLOBYTE(a3->dwValidParams) < 0 && a3->dwFeatures )
    {
      a3->dwFeatures = 0;
      v14 = 1;
    }
    (*(void (__fastcall **)(char *, struct IDirectMusicPort **))(*((_QWORD *)this + 8) + 8LL))((char *)this + 64, a4);
    v15 = *a4;
    v17 = 0;
    if ( ((__int64 (__fastcall *)(struct IDirectMusicPort *, GUID *, __int64 *))v15->lpVtbl->QueryInterface)(
           v15,
           &IID_IKsControl,
           &v17) >= 0 )
    {
      v18 = GUID_fedfae25_e46e_11d1_aace_0000f875ac12;
      v16 = 0;
      v21 = 0;
      v19 = 0;
      v20 = 2;
      (*(void (__fastcall **)(__int64, struct _GUID *, __int64, int *, int, int *))(*(_QWORD *)v17 + 24LL))(
        v17,
        &v18,
        24,
        &v16,
        4,
        &v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1800131a0  mov     [rsp-28h+arg_0], rbx
0x1800131a5  mov     [rsp-28h+arg_8], rsi
0x1800131aa  push    rbp
0x1800131ab  push    rdi
0x1800131ac  push    r12
0x1800131ae  push    r14
0x1800131b0  push    r15
0x1800131b2  mov     rbp, rsp
0x1800131b5  sub     rsp, 70h
0x1800131b9  mov     r12, r9
0x1800131bc  mov     rdi, r8
0x1800131bf  mov     r14, rcx
0x1800131c2  test    r9, r9
0x1800131c5  jz      loc_1800133EB
0x1800131cb  cmp     [rbp+arg_20], 0
0x1800131d0  jz      short loc_1800131DC
0x1800131d2  mov     eax, 80040110h
0x1800131d7  jmp     loc_1800133F0
0x1800131dc  test    rdx, rdx
0x1800131df  jz      loc_1800133EB
0x1800131e5  test    rdi, rdi
0x1800131e8  jz      short loc_180013202
0x1800131ea  cmp     dword ptr [r8], 20h ; ' '
0x1800131ee  jz      short loc_180013214
0x1800131f0  cmp     dword ptr [r8], 24h ; '$'
0x1800131f4  jz      short loc_18001320C
0x1800131f6  cmp     dword ptr [r8], 20h ; ' '
0x1800131fa  mov     r15d, 7
0x180013200  ja      short loc_18001321A
0x180013202  mov     eax, 80070057h
0x180013207  jmp     loc_1800133F0
0x18001320c  mov     r15d, 8
0x180013212  jmp     short loc_18001321A
0x180013214  mov     r15d, 7
0x18001321a  cmp     dword ptr [rcx+68h], 0
0x18001321e  xorps   xmm0, xmm0
0x180013221  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x180013225  jnz     short loc_180013231
0x180013227  mov     eax, 88781139h
0x18001322c  jmp     loc_1800133F0
0x180013231  mov     rax, [rdx]
0x180013234  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001323b  jnz     short loc_180013255
0x18001323d  mov     rax, [rdx+8]
0x180013241  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180013248  jnz     short loc_180013255
0x18001324a  lea     rdx, [rbp+var_20]; struct _GUID *
0x18001324e  call    ?GetDefaultPortI@CDirectMusic@@QEAAXPEAU_GUID@@@Z; CDirectMusic::GetDefaultPortI(_GUID *)
0x180013253  jmp     short loc_18001325D
0x180013255  movups  xmm0, xmmword ptr [rdx]
0x180013258  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001325d  lea     rbx, [r14+20h]
0x180013261  mov     qword ptr [r12], 0
0x180013269  mov     rax, [rbx]
0x18001326c  mov     rcx, rbx
0x18001326f  mov     rax, [rax+28h]
0x180013273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013278  test    rax, rax
0x18001327b  jnz     short loc_180013285
0x18001327d  mov     rcx, r14; this
0x180013280  call    ?UpdatePortList@CDirectMusic@@QEAAJXZ; CDirectMusic::UpdatePortList(void)
0x180013285  mov     rax, [rbx]
0x180013288  mov     rcx, rbx
0x18001328b  mov     rax, [rax+28h]
0x18001328f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013294  test    rax, rax
0x180013297  jz      short loc_1800132BA
0x180013299  mov     rcx, qword ptr [rbp+var_20.Data4]
0x18001329d  mov     rdx, qword ptr [rbp+var_20.Data1]
0x1800132a1  mov     rbx, [rax+10h]
0x1800132a5  cmp     [rbx+28h], rdx
0x1800132a9  jnz     short loc_1800132B1
0x1800132ab  cmp     [rbx+30h], rcx
0x1800132af  jz      short loc_1800132C4
0x1800132b1  mov     rax, [rax+8]
0x1800132b5  test    rax, rax
0x1800132b8  jnz     short loc_1800132A1
0x1800132ba  mov     eax, 80004002h
0x1800132bf  jmp     loc_1800133F0
0x1800132c4  test    rbx, rbx
0x1800132c7  jz      short loc_1800132BA
0x1800132c9  mov     ecx, [rbx]
0x1800132cb  sub     ecx, 1
0x1800132ce  jz      short loc_180013305
0x1800132d0  sub     ecx, 1
0x1800132d3  jz      short loc_1800132ED
0x1800132d5  cmp     ecx, 1
0x1800132d8  jnz     short loc_1800132BA
0x1800132da  mov     r9, r12; struct IDirectMusicPort **
0x1800132dd  mov     r8, rdi; struct _DMUS_PORTPARAMS8 *
0x1800132e0  mov     rdx, r14; struct CDirectMusic *
0x1800132e3  mov     rcx, rbx; struct tagPORTENTRY *
0x1800132e6  call    ?CreateCDirectMusicUMAPort@@YAJPEAUtagPORTENTRY@@PEAVCDirectMusic@@PEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@@Z; CreateCDirectMusicUMAPort(tagPORTENTRY *,CDirectMusic *,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *)
0x1800132eb  jmp     short loc_180013316
0x1800132ed  mov     r9, rdi; struct _DMUS_PORTPARAMS8 *
0x1800132f0  mov     [rsp+70h+var_50], r12; struct IDirectMusicPort **
0x1800132f5  mov     r8d, r15d; unsigned int
0x1800132f8  mov     rdx, r14; struct CDirectMusic *
0x1800132fb  mov     rcx, rbx; struct tagPORTENTRY *
0x1800132fe  call    ?CreateCDirectMusicSynthPort@@YAJPEAUtagPORTENTRY@@PEAVCDirectMusic@@IPEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@@Z; CreateCDirectMusicSynthPort(tagPORTENTRY *,CDirectMusic *,uint,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *)
0x180013303  jmp     short loc_180013316
0x180013305  mov     r9, r12; struct IDirectMusicPort **
0x180013308  mov     r8, rdi; struct _DMUS_PORTPARAMS8 *
0x18001330b  mov     rdx, r14; struct CDirectMusic *
0x18001330e  mov     rcx, rbx; struct tagPORTENTRY *
0x180013311  call    ?CreateCDirectMusicEmulatePort@@YAJPEAUtagPORTENTRY@@PEAVCDirectMusic@@PEAU_DMUS_PORTPARAMS8@@PEAPEAUIDirectMusicPort@@@Z; CreateCDirectMusicEmulatePort(tagPORTENTRY *,CDirectMusic *,_DMUS_PORTPARAMS8 *,IDirectMusicPort * *)
0x180013316  mov     esi, eax
0x180013318  test    eax, eax
0x18001331a  jns     short loc_180013323
0x18001331c  mov     eax, esi
0x18001331e  jmp     loc_1800133F0
0x180013323  cmp     dword ptr [rbx], 2
0x180013326  jz      short loc_180013346
0x180013328  cmp     r15d, 8
0x18001332c  jb      short loc_180013346
0x18001332e  test    byte ptr [rdi+4], 80h
0x180013332  jz      short loc_180013346
0x180013334  cmp     dword ptr [rdi+20h], 0
0x180013338  jz      short loc_180013346
0x18001333a  mov     dword ptr [rdi+20h], 0
0x180013341  mov     esi, 1
0x180013346  lea     rcx, [r14+40h]
0x18001334a  mov     rdx, r12
0x18001334d  mov     rax, [rcx]
0x180013350  mov     rax, [rax+8]
0x180013354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013359  mov     rcx, [r12]
0x18001335d  lea     r8, [rbp+var_28]
0x180013361  mov     [rbp+var_28], 0
0x180013369  lea     rdx, IID_IKsControl
0x180013370  mov     rax, [rcx]
0x180013373  mov     rax, [rax]
0x180013376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001337b  test    eax, eax
0x18001337d  js      short loc_18001331C
0x18001337f  movups  xmm0, xmmword ptr cs:_GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data1
0x180013386  mov     rcx, [rbp+var_28]
0x18001338a  lea     rdx, [rbp+arg_18]
0x18001338e  mov     [rsp+70h+var_48], rdx
0x180013393  lea     r9, [rbp+var_30]
0x180013397  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x18001339c  mov     [rbp+var_30], 0
0x1800133a3  lea     rdx, [rbp+var_20]
0x1800133a7  mov     [rbp+arg_18], 0
0x1800133ae  mov     r8d, 18h
0x1800133b4  mov     [rbp+var_10], 0
0x1800133bb  mov     [rbp+var_C], 2
0x1800133c2  mov     rax, [rcx]
0x1800133c5  mov     dword ptr [rsp+70h+var_50], 4
0x1800133cd  mov     rax, [rax+18h]
0x1800133d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133d6  mov     rcx, [rbp+var_28]
0x1800133da  mov     rax, [rcx]
0x1800133dd  mov     rax, [rax+10h]
0x1800133e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133e6  jmp     loc_18001331C
0x1800133eb  mov     eax, 80004003h
0x1800133f0  lea     r11, [rsp+70h+var_s0]
0x1800133f5  mov     rbx, [r11+30h]
0x1800133f9  mov     rsi, [r11+38h]
0x1800133fd  mov     rsp, r11
0x180013400  pop     r15
0x180013402  pop     r14
0x180013404  pop     r12
0x180013406  pop     rdi
0x180013407  pop     rbp
0x180013408  retn
```
