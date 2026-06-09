# CADMCOMW::QueryInterface(_GUID const &,void * *)

- ea: `0x180008240`
- end: `0x18000841f`
- name: `?QueryInterface@CADMCOMW@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `479`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180006c0c`
- `0x18000716c`
- `0x180008240`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::QueryInterface(CADMCOMW *this, const struct _GUID *a2, void **a3)
{
  int v6; // esi
  char *v8; // rax
  unsigned int v9; // [rsp+A0h] [rbp+18h] BYREF

  if ( !a3 )
    return (unsigned int)-2147024809;
  *a3 = 0;
  if ( *(_OWORD *)&IID_IMSAdminBase_EWR == *(_OWORD *)a2 )
  {
    *((_DWORD *)this + 224) = 1;
    return 2147500034LL;
  }
  if ( *((_DWORD *)this + 42) )
  {
    v6 = 0;
  }
  else
  {
    v6 = CADMCOMW::InitializeCallerWatch(this);
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMSAdminBase_W.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMSAdminBase_W.Data4
    || *(_QWORD *)&IID_IMSAdminBase2_W.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IMSAdminBase2_W.Data4 == *(_QWORD *)a2->Data4
    || *(_QWORD *)&IID_IMSAdminBase3_W.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IMSAdminBase3_W.Data4 == *(_QWORD *)a2->Data4 )
  {
    *a3 = this;
LABEL_25:
    (*(void (__fastcall **)(CADMCOMW *))(*(_QWORD *)this + 8LL))(this);
    return (unsigned int)v6;
  }
  if ( *(_QWORD *)&IID_IMSImpExpHelp_W.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IMSImpExpHelp_W.Data4 == *(_QWORD *)a2->Data4 )
  {
    v8 = (char *)this + 784;
LABEL_24:
    *a3 = v8;
    goto LABEL_25;
  }
  if ( *(_QWORD *)&IID_IConnectionPointContainer.Data1 == *(_QWORD *)&a2->Data1
    && *(_QWORD *)IID_IConnectionPointContainer.Data4 == *(_QWORD *)a2->Data4 )
  {
    v9 = 0;
    v6 = CADMCOMW::LookupAndAccessCheck(this, 0, &v9, 0, 2u, 0, 0, 0, 0, 0, 0);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v8 = (char *)this + 816;
    goto LABEL_24;
  }
  if ( *(_QWORD *)&IID_IMarshal.Data1 == *(_QWORD *)&a2->Data1 && *(_QWORD *)IID_IMarshal.Data4 == *(_QWORD *)a2->Data4 )
    return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 3))(
             *((_QWORD *)this + 3),
             a2,
             a3);
  return (unsigned int)-2147467262;
}

```

## disassembly

```asm
0x180008240  push    rbx
0x180008242  push    rsi
0x180008243  push    rdi
0x180008244  push    r14
0x180008246  sub     rsp, 68h
0x18000824a  mov     r14, r8
0x18000824d  mov     rdi, rdx
0x180008250  mov     rbx, rcx
0x180008253  test    r8, r8
0x180008256  jnz     short loc_180008262
0x180008258  mov     esi, 80070057h
0x18000825d  jmp     loc_180008413
0x180008262  mov     qword ptr [r8], 0
0x180008269  mov     rax, qword ptr cs:IID_IMSAdminBase_EWR.Data1
0x180008270  cmp     rax, [rdx]
0x180008273  jnz     short loc_180008296
0x180008275  mov     rax, qword ptr cs:IID_IMSAdminBase_EWR.Data4
0x18000827c  cmp     rax, [rdx+8]
0x180008280  jnz     short loc_180008296
0x180008282  mov     dword ptr [rcx+380h], 1
0x18000828c  mov     eax, 80004002h
0x180008291  jmp     loc_180008415
0x180008296  cmp     dword ptr [rcx+0A8h], 0
0x18000829d  jz      short loc_1800082A3
0x18000829f  xor     esi, esi
0x1800082a1  jmp     short loc_1800082B2
0x1800082a3  call    ?InitializeCallerWatch@CADMCOMW@@AEAAJXZ; CADMCOMW::InitializeCallerWatch(void)
0x1800082a8  mov     esi, eax
0x1800082aa  test    eax, eax
0x1800082ac  js      loc_180008413
0x1800082b2  mov     rcx, [rdi]
0x1800082b5  cmp     rcx, qword ptr cs:IID_IUnknown.Data1
0x1800082bc  jnz     short loc_1800082CB
0x1800082be  mov     rcx, [rdi+8]
0x1800082c2  cmp     rcx, qword ptr cs:IID_IUnknown.Data4
0x1800082c9  jz      short loc_180008316
0x1800082cb  mov     rax, [rdi]
0x1800082ce  cmp     rax, qword ptr cs:IID_IMSAdminBase_W.Data1
0x1800082d5  jnz     short loc_1800082E4
0x1800082d7  mov     rax, [rdi+8]
0x1800082db  cmp     rax, qword ptr cs:IID_IMSAdminBase_W.Data4
0x1800082e2  jz      short loc_180008316
0x1800082e4  mov     rax, qword ptr cs:IID_IMSAdminBase2_W.Data1
0x1800082eb  cmp     rax, [rdi]
0x1800082ee  jnz     short loc_1800082FD
0x1800082f0  mov     rax, qword ptr cs:IID_IMSAdminBase2_W.Data4
0x1800082f7  cmp     rax, [rdi+8]
0x1800082fb  jz      short loc_180008316
0x1800082fd  mov     rax, qword ptr cs:IID_IMSAdminBase3_W.Data1
0x180008304  cmp     rax, [rdi]
0x180008307  jnz     short loc_18000831E
0x180008309  mov     rax, qword ptr cs:IID_IMSAdminBase3_W.Data4
0x180008310  cmp     rax, [rdi+8]
0x180008314  jnz     short loc_18000831E
0x180008316  mov     [r14], rbx
0x180008319  jmp     loc_1800083CD
0x18000831e  mov     rax, qword ptr cs:IID_IMSImpExpHelp_W.Data1
0x180008325  cmp     rax, [rdi]
0x180008328  jnz     short loc_180008343
0x18000832a  mov     rax, qword ptr cs:IID_IMSImpExpHelp_W.Data4
0x180008331  cmp     rax, [rdi+8]
0x180008335  jnz     short loc_180008343
0x180008337  lea     rax, [rbx+310h]
0x18000833e  jmp     loc_1800083CA
0x180008343  mov     rax, qword ptr cs:IID_IConnectionPointContainer.Data1
0x18000834a  cmp     rax, [rdi]
0x18000834d  jnz     loc_1800083DE
0x180008353  mov     rax, qword ptr cs:IID_IConnectionPointContainer.Data4
0x18000835a  cmp     rax, [rdi+8]
0x18000835e  jnz     short loc_1800083DE
0x180008360  mov     [rsp+88h+var_38], 0
0x180008369  lea     r8, [rsp+88h+arg_10]
0x180008371  mov     [rsp+88h+var_40], 0
0x18000837a  xor     r9d, r9d
0x18000837d  mov     [rsp+88h+var_48], 0
0x180008386  xor     edx, edx
0x180008388  mov     [rsp+88h+var_50], 0
0x180008391  mov     rcx, rbx
0x180008394  mov     [rsp+88h+var_58], 0
0x18000839d  mov     [rsp+88h+var_60], 0
0x1800083a5  mov     [rsp+88h+var_68], 2
0x1800083ad  mov     [rsp+88h+arg_10], 0
0x1800083b8  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x1800083bd  mov     esi, eax
0x1800083bf  test    eax, eax
0x1800083c1  js      short loc_180008413
0x1800083c3  lea     rax, [rbx+330h]
0x1800083ca  mov     [r14], rax
0x1800083cd  mov     rax, [rbx]
0x1800083d0  mov     rcx, rbx
0x1800083d3  mov     rax, [rax+8]
0x1800083d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083dc  jmp     short loc_180008413
0x1800083de  mov     rax, qword ptr cs:IID_IMarshal.Data1
0x1800083e5  cmp     rax, [rdi]
0x1800083e8  jnz     short loc_18000840E
0x1800083ea  mov     rax, qword ptr cs:IID_IMarshal.Data4
0x1800083f1  cmp     rax, [rdi+8]
0x1800083f5  jnz     short loc_18000840E
0x1800083f7  mov     rcx, [rbx+18h]
0x1800083fb  mov     r8, r14
0x1800083fe  mov     rdx, rdi
0x180008401  mov     rax, [rcx]
0x180008404  mov     rax, [rax]
0x180008407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000840c  jmp     short loc_180008415
0x18000840e  mov     esi, 80004002h
0x180008413  mov     eax, esi
0x180008415  add     rsp, 68h
0x180008419  pop     r14
0x18000841b  pop     rdi
0x18000841c  pop     rsi
0x18000841d  pop     rbx
0x18000841e  retn
```
