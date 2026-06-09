# JSONStringifyWalkObjectMembers(BuildString &,CSession *,VAR *,VAR *,ushort *,uint &,bool &)

- ea: `0x18006ba00`
- end: `0x18006bcdd`
- name: `?JSONStringifyWalkObjectMembers@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@2PEAGAEAIAEA_N@Z`
- size: `733`
- prototype: `int __fastcall(struct BuildString *, struct CSession *, struct VAR *, struct VAR *, unsigned __int16 *, unsigned int *, struct NameTbl *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18006b63c`

## callees

- `0x180005070`
- `0x1800076e0`
- `0x180007e68`
- `0x18000d190`
- `0x180039f20`
- `0x18006b478`
- `0x18006b7b4`
- `0x18006ba00`
- `0x180077cf4`
- `0x180098010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006bc03`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bcab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bc03`
- `OLEAUT32!__imp_SysFreeString` at `0x18006bcab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800973f7`

## pseudocode

```c
int __fastcall JSONStringifyWalkObjectMembers(
        struct BuildString *a1,
        struct CSession *a2,
        struct VAR *a3,
        struct VAR *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        struct NameTbl *a7)
{
  struct VAR *v11; // rbx
  VAR *v12; // r9
  bool *v13; // r15
  unsigned int v15; // edx
  NameTbl *v16; // rcx
  int v17; // r13d
  OLECHAR *v18; // rdi
  int NextOwnIdSym; // eax
  int v20; // ebx
  int v21; // eax
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  VAR *v24; // [rsp+58h] [rbp-B0h]
  NameTbl *v25; // [rsp+60h] [rbp-A8h]
  unsigned __int16 *v26[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+78h] [rbp-90h]
  __int16 *v28; // [rsp+80h] [rbp-88h] BYREF
  struct CSession *v29; // [rsp+88h] [rbp-80h]
  __int64 v30; // [rsp+90h] [rbp-78h]
  __int16 v31; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 *v32; // [rsp+A0h] [rbp-68h]
  __int128 v33; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+C8h] [rbp-40h] BYREF
  int v37; // [rsp+128h] [rbp+20h] BYREF

  v11 = VAR::PvarCutAll(a3);
  v13 = (bool *)a7;
  *(_BYTE *)a7 = 1;
  a7 = 0;
  if ( v12
    && (unsigned int)VAR::IsJsObj(v12, &a7)
    && (*(unsigned int (__fastcall **)(struct NameTbl *))(*(_QWORD *)a7 + 240LL))(a7) )
  {
    return JSONStringifyObjectMembersByArrayReplacer(a1, a2, a3, a4, a5, a6, v13);
  }
  v33 = *(_OWORD *)v11;
  v34 = *((_QWORD *)v11 + 2);
  v24 = VAR::PvarCutHeap((VAR *)&v33);
  v16 = (NameTbl *)*((_QWORD *)v24 + 1);
  v25 = v16;
  v17 = -1;
  v37 = -1;
  v18 = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v31 = 8;
  v29 = a2;
  v28 = &v31;
  v30 = *((_QWORD *)a2 + 122);
  *((_QWORD *)a2 + 122) = &v28;
  LOBYTE(a7) = 1;
  while ( 1 )
  {
    NextOwnIdSym = NameTbl::GetNextOwnIdSym(v16, v15, v17, &v37, (struct SYM *)v26);
    v20 = NextOwnIdSym;
    if ( NextOwnIdSym < 0 )
      break;
    if ( NextOwnIdSym > 0 )
    {
      v20 = 0;
      *v13 = (char)a7;
      break;
    }
    v17 = v37;
    v21 = VAR::InvokeByDispID(v24, a2, v37, 2u, &pvarg, 0, 0, 0);
    v20 = v21;
    if ( v21 < 0 )
      break;
    if ( !v21 )
    {
      if ( v18 )
        SysFreeString(v18);
      v22 = _SysAllocStringLen(v26[0], (unsigned int)v26[1]);
      v18 = v22;
      if ( !v22 )
      {
        v20 = -2147024882;
        break;
      }
      v32 = v22;
      v20 = JSONStringifyObjectMember(a1, a2, (struct VAR *)&v31, (struct VAR *)&pvarg, a4, a5, a6, (bool *)&a7, a3);
      if ( v20 < 0 )
        break;
    }
    v16 = v25;
  }
  if ( v18 )
    SysFreeString(v18);
  v23 = *((_QWORD *)v29 + 122);
  if ( v23 )
    *((_QWORD *)v29 + 122) = *(_QWORD *)(v23 + 16);
  return v20;
}

```

## disassembly

```asm
0x18006ba00  mov     [rsp+arg_8], rbx
0x18006ba05  mov     [rsp+arg_10], rsi
0x18006ba0a  mov     [rsp+arg_0], rcx
0x18006ba0f  push    rdi
0x18006ba10  push    r12
0x18006ba12  push    r13
0x18006ba14  push    r14
0x18006ba16  push    r15
0x18006ba18  sub     rsp, 0E0h
0x18006ba1f  mov     rsi, r9
0x18006ba22  mov     r12, r8
0x18006ba25  mov     r14, rdx
0x18006ba28  mov     rdi, rcx
0x18006ba2b  mov     rcx, r8; this
0x18006ba2e  call    ?PvarCutAll@VAR@@QEAAPEAV1@XZ; VAR::PvarCutAll(void)
0x18006ba33  mov     rbx, rax
0x18006ba36  mov     r15, [rsp+108h+arg_30]
0x18006ba3e  mov     byte ptr [r15], 1
0x18006ba42  mov     [rsp+108h+arg_30], 0
0x18006ba4e  test    r9, r9
0x18006ba51  jz      short loc_18006BAD0
0x18006ba53  lea     rdx, [rsp+108h+arg_30]; struct NameTbl **
0x18006ba5b  mov     rcx, r9; this
0x18006ba5e  call    ?IsJsObj@VAR@@QEAAHPEAPEAVNameTbl@@@Z; VAR::IsJsObj(NameTbl * *)
0x18006ba63  test    eax, eax
0x18006ba65  jz      short loc_18006BAD0
0x18006ba67  mov     rcx, [rsp+108h+arg_30]
0x18006ba6f  mov     rax, [rcx]
0x18006ba72  mov     rax, [rax+0F0h]
0x18006ba79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba7e  test    eax, eax
0x18006ba80  jz      short loc_18006BAD0
0x18006ba82  mov     [rsp+108h+var_D8], r15; bool *
0x18006ba87  mov     rax, [rsp+108h+arg_28]
0x18006ba8f  mov     [rsp+108h+var_E0], rax; unsigned int *
0x18006ba94  mov     rax, [rsp+108h+arg_20]
0x18006ba9c  mov     [rsp+108h+pvarg], rax; unsigned __int16 *
0x18006baa1  mov     r9, rsi; struct VAR *
0x18006baa4  mov     r8, r12; struct VAR *
0x18006baa7  mov     rdx, r14; struct CSession *
0x18006baaa  mov     rcx, rdi; struct BuildString *
0x18006baad  call    ?JSONStringifyObjectMembersByArrayReplacer@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@2PEAGAEAIAEA_N@Z; JSONStringifyObjectMembersByArrayReplacer(BuildString &,CSession *,VAR *,VAR *,ushort *,uint &,bool &)
0x18006bab2  lea     r11, [rsp+108h+var_28]
0x18006baba  mov     rbx, [r11+38h]
0x18006babe  mov     rsi, [r11+40h]
0x18006bac2  mov     rsp, r11
0x18006bac5  pop     r15
0x18006bac7  pop     r14
0x18006bac9  pop     r13
0x18006bacb  pop     r12
0x18006bacd  pop     rdi
0x18006bace  retn
0x18006bad0  movups  xmm0, xmmword ptr [rbx]
0x18006bad3  movups  [rsp+108h+var_58], xmm0
0x18006badb  movsd   xmm1, qword ptr [rbx+10h]
0x18006bae0  movsd   [rsp+108h+var_48], xmm1
0x18006bae9  lea     rcx, [rsp+108h+var_58]; this
0x18006baf1  call    ?PvarCutHeap@VAR@@QEAAPEAV1@XZ; VAR::PvarCutHeap(void)
0x18006baf6  mov     [rsp+108h+var_B0], rax
0x18006bafb  mov     rcx, [rax+8]; this
0x18006baff  mov     [rsp+108h+var_A8], rcx
0x18006bb04  or      r13d, 0FFFFFFFFh
0x18006bb08  mov     [rsp+108h+arg_18], r13d
0x18006bb10  xor     edi, edi
0x18006bb12  mov     [rsp+108h+var_B8], rdi
0x18006bb17  xorps   xmm0, xmm0
0x18006bb1a  xor     eax, eax
0x18006bb1c  movups  xmmword ptr [rsp+108h+var_A0], xmm0
0x18006bb21  mov     [rsp+108h+var_90], rax
0x18006bb26  lea     eax, [rdi+8]
0x18006bb29  mov     [rsp+108h+var_70], ax
0x18006bb31  mov     [rsp+108h+var_80], r14
0x18006bb39  lea     rax, [rsp+108h+var_70]
0x18006bb41  mov     [rsp+108h+var_88], rax
0x18006bb49  mov     rax, [r14+3D0h]
0x18006bb50  mov     [rsp+108h+var_78], rax
0x18006bb58  lea     rax, [rsp+108h+var_88]
0x18006bb60  mov     [r14+3D0h], rax
0x18006bb67  mov     byte ptr [rsp+108h+arg_30], 1
0x18006bb6f  lea     rax, [rsp+108h+var_A0]
0x18006bb74  mov     [rsp+108h+pvarg], rax; struct SYM *
0x18006bb79  lea     r9, [rsp+108h+arg_18]; int *
0x18006bb81  mov     r8d, r13d; int
0x18006bb84  call    ?GetNextOwnIdSym@NameTbl@@QEAAJKJPEAJPEAUSYM@@@Z; NameTbl::GetNextOwnIdSym(ulong,long,long *,SYM *)
0x18006bb89  mov     ebx, eax
0x18006bb8b  test    eax, eax
0x18006bb8d  js      loc_18006BCA3
0x18006bb93  jle     short loc_18006BBA6
0x18006bb95  xor     ebx, ebx
0x18006bb97  mov     al, byte ptr [rsp+108h+arg_30]
0x18006bb9e  mov     [r15], al
0x18006bba1  jmp     loc_18006BCA3
0x18006bba6  mov     [rsp+108h+var_D0], 0; struct VAR *
0x18006bbaf  mov     [rsp+108h+var_D8], 0; struct VAR *
0x18006bbb8  mov     dword ptr [rsp+108h+var_E0], 0; int
0x18006bbc0  lea     rax, [rsp+108h+var_40]
0x18006bbc8  mov     [rsp+108h+pvarg], rax; pvarg
0x18006bbcd  mov     r9d, 2; unsigned int
0x18006bbd3  mov     r13d, [rsp+108h+arg_18]
0x18006bbdb  mov     r8d, r13d; int
0x18006bbde  mov     rdx, r14; struct CSession *
0x18006bbe1  mov     rcx, [rsp+108h+var_B0]; this
0x18006bbe6  call    ?InvokeByDispID@VAR@@QEAAJPEAVCSession@@JKPEAV1@H11@Z; VAR::InvokeByDispID(CSession *,long,ulong,VAR *,int,VAR *,VAR *)
0x18006bbeb  mov     ebx, eax
0x18006bbed  test    eax, eax
0x18006bbef  js      loc_18006BCA3
0x18006bbf5  jnz     loc_18006BC99
0x18006bbfb  test    rdi, rdi
0x18006bbfe  jz      short loc_18006BC18
0x18006bc00  mov     rcx, rdi; bstrString
0x18006bc03  call    cs:__imp_SysFreeString
0x18006bc0a  nop     dword ptr [rax+rax+00h]
0x18006bc0f  mov     [rsp+108h+var_B8], 0
0x18006bc18  mov     edx, dword ptr [rsp+108h+var_A0+8]; unsigned int
0x18006bc1c  mov     rcx, [rsp+108h+var_A0]; unsigned __int16 *
0x18006bc21  call    ?_SysAllocStringLen@@YAPEAGPEBGI@Z; _SysAllocStringLen(ushort const *,uint)
0x18006bc26  mov     rdi, rax
0x18006bc29  mov     [rsp+108h+var_B8], rax
0x18006bc2e  test    rax, rax
0x18006bc31  jnz     short loc_18006BC3A
0x18006bc33  mov     ebx, 8007000Eh
0x18006bc38  jmp     short loc_18006BCA3
0x18006bc3a  mov     [rsp+108h+var_68], rax
0x18006bc42  mov     [rsp+108h+var_C8], r12; struct VAR *
0x18006bc47  lea     rax, [rsp+108h+arg_30]
0x18006bc4f  mov     [rsp+108h+var_D0], rax; bool *
0x18006bc54  mov     rax, [rsp+108h+arg_28]
0x18006bc5c  mov     [rsp+108h+var_D8], rax; unsigned int *
0x18006bc61  mov     rax, [rsp+108h+arg_20]
0x18006bc69  mov     [rsp+108h+var_E0], rax; unsigned __int16 *
0x18006bc6e  mov     [rsp+108h+pvarg], rsi; struct VAR *
0x18006bc73  lea     r9, [rsp+108h+var_40]; struct VAR *
0x18006bc7b  lea     r8, [rsp+108h+var_70]; struct VAR *
0x18006bc83  mov     rdx, r14; struct CSession *
0x18006bc86  mov     rcx, [rsp+108h+arg_0]; this
0x18006bc8e  call    ?JSONStringifyObjectMember@@YAJAEAVBuildString@@PEAVCSession@@PEAVVAR@@22PEAGAEAIAEA_N2@Z; JSONStringifyObjectMember(BuildString &,CSession *,VAR *,VAR *,VAR *,ushort *,uint &,bool &,VAR *)
0x18006bc93  mov     ebx, eax
0x18006bc95  test    eax, eax
0x18006bc97  js      short loc_18006BCA3
0x18006bc99  mov     rcx, [rsp+108h+var_A8]
0x18006bc9e  jmp     loc_18006BB6F
0x18006bca3  test    rdi, rdi
0x18006bca6  jz      short loc_18006BCB7
0x18006bca8  mov     rcx, rdi; bstrString
0x18006bcab  call    cs:__imp_SysFreeString
0x18006bcb2  nop     dword ptr [rax+rax+00h]
0x18006bcb7  mov     rcx, [rsp+108h+var_80]
0x18006bcbf  mov     rax, [rcx+3D0h]
0x18006bcc6  test    rax, rax
0x18006bcc9  jz      short loc_18006BCD6
0x18006bccb  mov     rax, [rax+10h]
0x18006bccf  mov     [rcx+3D0h], rax
0x18006bcd6  mov     eax, ebx
0x18006bcd8  jmp     loc_18006BAB2
0x1800973e5  push    rbp
0x1800973e7  sub     rsp, 50h
0x1800973eb  mov     rbp, rdx
0x1800973ee  mov     rcx, [rbp+50h]; bstrString
0x1800973f2  test    rcx, rcx
0x1800973f5  jz      short loc_180097404
0x1800973f7  call    cs:__imp_SysFreeString
0x1800973fe  nop     dword ptr [rax+rax+00h]
0x180097403  nop
0x180097404  add     rsp, 50h
0x180097408  pop     rbp
0x180097409  retn
```
