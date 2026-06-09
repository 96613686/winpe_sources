# RegExpObj::Compile(int,VAR *)

- ea: `0x180003e0c`
- end: `0x180004277`
- name: `?Compile@RegExpObj@@QEAAJHPEAVVAR@@@Z`
- size: `1131`
- prototype: `__int64 __fastcall(struct CSession **this, int, struct VAR *)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180044d20`
- `0x180044eb4`
- `0x180070ab0`

## callees

- `0x180003460`
- `0x180003e0c`
- `0x180004280`
- `0x180005b44`
- `0x180007e9c`
- `0x1800090b0`
- `0x18000b9ac`
- `0x18002c884`
- `0x18002cb6c`
- `0x180034980`
- `0x180036bcc`
- `0x18004a940`
- `0x18004de04`
- `0x1800585c4`
- `0x1800585d0`
- `0x18006f938`
- `0x18008859c`
- `0x180096692`
- `0x180098010`

## import_xrefs

- `msvcrt!free` at `0x1800041f0`
- `msvcrt!free` at `0x1800041f0`
- `OLEAUT32!__imp_SysStringLen` at `0x180003edb`
- `OLEAUT32!__imp_SysStringLen` at `0x180003f57`
- `OLEAUT32!__imp_SysStringLen` at `0x18000416d`
- `OLEAUT32!__imp_SysStringLen` at `0x180004198`
- `OLEAUT32!__imp_SysStringLen` at `0x180003edb`
- `OLEAUT32!__imp_SysStringLen` at `0x180003f57`
- `OLEAUT32!__imp_SysStringLen` at `0x18000416d`
- `OLEAUT32!__imp_SysStringLen` at `0x180004198`

## pseudocode

```c
__int64 __fastcall RegExpObj::Compile(struct CSession **this, int a2, struct VAR *a3)
{
  __int64 v4; // r15
  UINT v6; // ebx
  RegExpComp *v7; // rsi
  unsigned __int16 *v8; // r12
  unsigned __int16 *v9; // r13
  struct RegExpObj *RegExp; // rdi
  int String; // ebx
  RegExpComp *v12; // rax
  struct VAR *v13; // rax
  struct VAR *v14; // rbx
  __int64 v15; // rax
  RegExpExec *v16; // r15
  VAR *v17; // r12
  unsigned __int16 *v18; // r12
  int v19; // r13d
  RegExpExec *v20; // rax
  RegExpExec *v21; // rcx
  unsigned int v22; // edx
  RegExpExec *v23; // rcx
  unsigned int v24; // edx
  UINT len; // [rsp+40h] [rbp-108h] BYREF
  struct VAR *v27; // [rsp+48h] [rbp-100h] BYREF
  UINT v28; // [rsp+50h] [rbp-F8h]
  UINT v29; // [rsp+54h] [rbp-F4h]
  UINT v30; // [rsp+58h] [rbp-F0h]
  void *Src; // [rsp+60h] [rbp-E8h] BYREF
  unsigned __int16 *v32; // [rsp+68h] [rbp-E0h]
  unsigned __int16 *v33; // [rsp+70h] [rbp-D8h]
  RegExpComp *v34; // [rsp+78h] [rbp-D0h]
  _BYTE v35[8]; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+88h] [rbp-C0h]
  VARIANTARG v37; // [rsp+A0h] [rbp-A8h] BYREF
  _BYTE v38[8]; // [rsp+B8h] [rbp-90h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-88h]
  VARIANTARG v40; // [rsp+D8h] [rbp-70h] BYREF
  _BYTE v41[8]; // [rsp+F0h] [rbp-58h] BYREF
  __int64 v42; // [rsp+F8h] [rbp-50h]
  _BYTE v43[8]; // [rsp+108h] [rbp-40h] BYREF
  __int64 v44; // [rsp+110h] [rbp-38h]
  UINT v46; // [rsp+168h] [rbp+20h]

  v4 = a2;
  v6 = 0;
  v7 = 0;
  Src = 0;
  len = 0;
  ScavVariant::ScavVariant((ScavVariant *)v35);
  ScavVariant::ScavVariant((ScavVariant *)v38);
  v8 = (unsigned __int16 *)&::String;
  v9 = (unsigned __int16 *)&::String;
  v46 = 0;
  v29 = 0;
  if ( (int)v4 <= 0 )
  {
LABEL_10:
    v12 = (RegExpComp *)operator new(0x160u);
    if ( v12 )
      v7 = RegExpComp::RegExpComp(v12);
    else
      v7 = 0;
    v34 = v7;
    if ( v7 )
    {
      String = RegExpComp::CompileDynamic(v7, v8, v46, v9, v6, (unsigned __int8 **)&Src, (int *)&len);
      if ( String < 0 )
        goto LABEL_35;
      v13 = PvarAllocBstrByteLen(len, this[3]);
      v14 = v13;
      if ( v13 )
      {
        memcpy_0(*((void **)v13 + 1), Src, (int)len);
        *((_WORD *)this + 52) = 128;
        this[14] = v14;
        *((_WORD *)this + 64) = 0;
        *((_WORD *)this + 76) = 0;
        *((_WORD *)this + 88) = 0;
        *((_WORD *)this + 100) = 0;
        *((_WORD *)this + 112) = 0;
        *((_WORD *)this + 124) = 0;
        *((_WORD *)this + 136) = 3;
        *((_DWORD *)this + 70) = 0;
        *((_DWORD *)this + 74) = 0;
        String = 0;
        goto LABEL_35;
      }
    }
    goto LABEL_17;
  }
  v27 = (struct VAR *)((char *)a3 + 24 * v4 - 24);
  RegExp = GetRegExp(v27);
  if ( !RegExp )
  {
    if ( *(_WORD *)v27 )
    {
      String = ConvertToString(this[3], (struct IDispatch ***)&v27, &v37, 1);
      if ( String < 0 )
        goto LABEL_35;
      v8 = (unsigned __int16 *)*((_QWORD *)v27 + 1);
      v32 = v8;
      v46 = SysStringLen(v8);
      v28 = v46;
      v6 = v29;
    }
    if ( (int)v4 >= 2 )
    {
      v27 = (struct VAR *)((char *)a3 + 24 * v4 - 48);
      if ( *(_WORD *)v27 )
      {
        String = ConvertToString(this[3], (struct IDispatch ***)&v27, &v40, 1);
        if ( String < 0 )
          goto LABEL_35;
        v9 = (unsigned __int16 *)*((_QWORD *)v27 + 1);
        v33 = v9;
        v6 = SysStringLen(v9);
        v30 = v6;
      }
    }
    goto LABEL_10;
  }
  if ( (int)v4 < 2 )
  {
    v16 = 0;
  }
  else
  {
    v15 = 3 * (v4 - 2);
    v16 = 0;
    if ( *((_WORD *)a3 + 4 * v15) )
    {
      (*(void (__fastcall **)(struct RegExpObj *))(*(_QWORD *)RegExp + 16LL))(RegExp);
      String = -2146823271;
      goto LABEL_35;
    }
  }
  if ( *((_WORD *)RegExp + 52) != 128 )
  {
LABEL_33:
    (*(void (__fastcall **)(struct RegExpObj *))(*(_QWORD *)RegExp + 16LL))(RegExp);
    goto LABEL_10;
  }
  v17 = (VAR *)*((_QWORD *)RegExp + 14);
  if ( !(unsigned int)VAR::FBstr(v17) || (v18 = (unsigned __int16 *)*((_QWORD *)v17 + 1)) == 0 )
  {
    v8 = (unsigned __int16 *)&::String;
    goto LABEL_33;
  }
  v19 = CbBstr(v18);
  v20 = (RegExpExec *)operator new(0x1E0u);
  if ( v20 )
    v16 = RegExpExec::RegExpExec(v20);
  if ( !v16 )
  {
LABEL_17:
    String = -2147024882;
    goto LABEL_35;
  }
  String = RegExpExec::GetString(v21, this[3], (unsigned __int8 *)v18, v19, (struct VAR *)v41, 0);
  if ( String >= 0 )
  {
    String = RegExpExec::GetString(v23, this[3], (unsigned __int8 *)v18, v19, (struct VAR *)v43, 1);
    if ( String >= 0 )
    {
      v8 = *(unsigned __int16 **)(v42 + 8);
      v32 = v8;
      v46 = SysStringLen(v8);
      v28 = v46;
      v9 = *(unsigned __int16 **)(v44 + 8);
      v33 = v9;
      v6 = SysStringLen(v9);
      v30 = v6;
      RegExpExec::`scalar deleting destructor'(v16, v24);
      goto LABEL_33;
    }
  }
  RegExpExec::`scalar deleting destructor'(v16, v22);
  (*(void (__fastcall **)(struct RegExpObj *))(*(_QWORD *)RegExp + 16LL))(RegExp);
LABEL_35:
  free(Src);
  if ( v7 )
  {
    RegExpComp::~RegExpComp(v7);
    operator delete(v7);
  }
  if ( v36 && (*(_BYTE *)(v36 + 12) & 8) == 0 )
    IScavengerBase::Close((IScavengerBase *)v35);
  if ( v39 && (*(_BYTE *)(v39 + 12) & 8) == 0 )
    IScavengerBase::Close((IScavengerBase *)v38);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180003e0c  mov     rax, rsp
0x180003e0f  mov     [rax+8], rbx
0x180003e13  mov     [rax+10h], rsi
0x180003e17  mov     [rax+18h], r8
0x180003e1b  push    rdi
0x180003e1c  push    r12
0x180003e1e  push    r13
0x180003e20  push    r14
0x180003e22  push    r15
0x180003e24  sub     rsp, 120h
0x180003e2b  mov     rdi, r8
0x180003e2e  movsxd  r15, edx
0x180003e31  mov     r14, rcx
0x180003e34  xor     ebx, ebx
0x180003e36  mov     esi, ebx
0x180003e38  mov     [rsp+148h+Src], rbx
0x180003e3d  mov     [rsp+148h+len], ebx
0x180003e41  lea     rcx, [rax-0C8h]; this
0x180003e48  call    ??0ScavVariant@@QEAA@XZ; ScavVariant::ScavVariant(void)
0x180003e4d  lea     rcx, [rsp+148h+var_90]; this
0x180003e55  call    ??0ScavVariant@@QEAA@XZ; ScavVariant::ScavVariant(void)
0x180003e5a  lea     r12, String
0x180003e61  mov     r13, r12
0x180003e64  mov     [rsp+148h+arg_18], ebx
0x180003e6b  mov     [rsp+148h+var_F4], ebx
0x180003e6f  test    r15d, r15d
0x180003e72  jle     loc_1800041E3
0x180003e78  lea     rax, [r15-1]
0x180003e7c  lea     rcx, [rax+rax*2]
0x180003e80  lea     rcx, [rdi+rcx*8]; struct VAR *
0x180003e84  mov     [rsp+148h+var_100], rcx
0x180003e89  call    ?GetRegExp@@YAPEAVRegExpObj@@PEAVVAR@@@Z; GetRegExp(VAR *)
0x180003e8e  mov     rdi, rax
0x180003e91  xor     ecx, ecx
0x180003e93  test    rax, rax
0x180003e96  jnz     loc_180004068
0x180003e9c  mov     rax, [rsp+148h+var_100]
0x180003ea1  cmp     [rax], cx
0x180003ea4  jz      short loc_180003EF6
0x180003ea6  lea     r9d, [rbx+1]; int
0x180003eaa  lea     r8, [rsp+148h+var_A8]; struct VAR *
0x180003eb2  lea     rdx, [rsp+148h+var_100]; struct VAR **
0x180003eb7  mov     rcx, [r14+18h]; struct CSession *
0x180003ebb  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180003ec0  mov     ebx, eax
0x180003ec2  test    eax, eax
0x180003ec4  js      loc_1800041EB
0x180003eca  mov     rax, [rsp+148h+var_100]
0x180003ecf  mov     r12, [rax+8]
0x180003ed3  mov     [rsp+148h+var_E0], r12
0x180003ed8  mov     rcx, r12; pbstr
0x180003edb  call    cs:__imp_SysStringLen
0x180003ee2  nop     dword ptr [rax+rax+00h]
0x180003ee7  mov     [rsp+148h+arg_18], eax
0x180003eee  mov     [rsp+148h+var_F8], eax
0x180003ef2  mov     ebx, [rsp+148h+var_F4]
0x180003ef6  cmp     r15d, 2
0x180003efa  jl      loc_1800041E3
0x180003f00  lea     rax, [r15-2]
0x180003f04  lea     rax, [rax+rax*2]
0x180003f08  mov     rcx, [rsp+148h+arg_10]
0x180003f10  lea     rcx, [rcx+rax*8]
0x180003f14  mov     [rsp+148h+var_100], rcx
0x180003f19  xor     r15d, r15d
0x180003f1c  cmp     [rcx], r15w
0x180003f20  jz      short loc_180003F69
0x180003f22  lea     r9d, [r15+1]; int
0x180003f26  lea     r8, [rsp+148h+var_70]; struct VAR *
0x180003f2e  lea     rdx, [rsp+148h+var_100]; struct VAR **
0x180003f33  mov     rcx, [r14+18h]; struct CSession *
0x180003f37  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180003f3c  mov     ebx, eax
0x180003f3e  test    eax, eax
0x180003f40  js      loc_1800041EB
0x180003f46  mov     rax, [rsp+148h+var_100]
0x180003f4b  mov     r13, [rax+8]
0x180003f4f  mov     [rsp+148h+var_D8], r13
0x180003f54  mov     rcx, r13; pbstr
0x180003f57  call    cs:__imp_SysStringLen
0x180003f5e  nop     dword ptr [rax+rax+00h]
0x180003f63  mov     ebx, eax
0x180003f65  mov     [rsp+148h+var_F0], eax
0x180003f69  mov     edi, 80h
0x180003f6e  mov     ecx, 160h; Size
0x180003f73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f78  test    rax, rax
0x180003f7b  jz      loc_180004056
0x180003f81  mov     rcx, rax; this
0x180003f84  call    ??0RegExpComp@@QEAA@XZ; RegExpComp::RegExpComp(void)
0x180003f89  mov     rsi, rax
0x180003f8c  mov     [rsp+148h+var_D0], rsi
0x180003f91  test    rsi, rsi
0x180003f94  jz      loc_18000405E
0x180003f9a  lea     rax, [rsp+148h+len]
0x180003f9f  mov     [rsp+148h+var_118], rax; int *
0x180003fa4  lea     rax, [rsp+148h+Src]
0x180003fa9  mov     [rsp+148h+var_120], rax; unsigned __int8 **
0x180003fae  mov     dword ptr [rsp+148h+var_128], ebx; int
0x180003fb2  mov     r9, r13; unsigned __int16 *
0x180003fb5  mov     r8d, [rsp+148h+arg_18]; int
0x180003fbd  mov     rdx, r12; unsigned __int16 *
0x180003fc0  mov     rcx, rsi; this
0x180003fc3  call    ?CompileDynamic@RegExpComp@@QEAAJPEBGJ0JPEAPEAEPEAJ@Z; RegExpComp::CompileDynamic(ushort const *,long,ushort const *,long,uchar * *,long *)
0x180003fc8  mov     ebx, eax
0x180003fca  test    eax, eax
0x180003fcc  js      loc_1800041EB
0x180003fd2  mov     rdx, [r14+18h]; struct CSession *
0x180003fd6  mov     ecx, [rsp+148h+len]; len
0x180003fda  call    ?PvarAllocBstrByteLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrByteLen(long,CSession *)
0x180003fdf  mov     rbx, rax
0x180003fe2  test    rax, rax
0x180003fe5  jz      short loc_18000405E
0x180003fe7  movsxd  r8, [rsp+148h+len]; Size
0x180003fec  mov     rdx, [rsp+148h+Src]; Src
0x180003ff1  mov     rcx, [rax+8]; void *
0x180003ff5  call    memcpy_0
0x180003ffa  mov     [r14+68h], di
0x180003fff  mov     [r14+70h], rbx
0x180004003  mov     [r14+80h], r15w
0x18000400b  mov     [r14+98h], r15w
0x180004013  mov     [r14+0B0h], r15w
0x18000401b  mov     [r14+0C8h], r15w
0x180004023  mov     [r14+0E0h], r15w
0x18000402b  mov     [r14+0F8h], r15w
0x180004033  mov     eax, 3
0x180004038  mov     [r14+110h], ax
0x180004040  mov     [r14+118h], r15d
0x180004047  mov     [r14+128h], r15d
0x18000404e  mov     ebx, r15d
0x180004051  jmp     loc_1800041EB
0x180004056  mov     rsi, r15
0x180004059  jmp     loc_180003F8C
0x18000405e  mov     ebx, 8007000Eh
0x180004063  jmp     loc_1800041EB
0x180004068  cmp     r15d, 2
0x18000406c  jl      short loc_1800040A1
0x18000406e  lea     rax, [r15-2]
0x180004072  lea     rax, [rax+rax*2]
0x180004076  mov     rcx, [rsp+148h+arg_10]
0x18000407e  xor     r15d, r15d
0x180004081  cmp     [rcx+rax*8], r15w
0x180004086  jz      short loc_1800040A4
0x180004088  mov     rax, [rdi]
0x18000408b  mov     rcx, rdi
0x18000408e  mov     rax, [rax+10h]
0x180004092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004097  mov     ebx, 800A1399h
0x18000409c  jmp     loc_1800041EB
0x1800040a1  xor     r15d, r15d
0x1800040a4  mov     eax, 80h
0x1800040a9  cmp     ax, [rdi+68h]
0x1800040ad  jnz     loc_1800041D4
0x1800040b3  mov     r12, [rdi+70h]
0x1800040b7  mov     rcx, r12; this
0x1800040ba  call    ?FBstr@VAR@@QEAAHXZ; VAR::FBstr(void)
0x1800040bf  test    eax, eax
0x1800040c1  jz      loc_1800041CD
0x1800040c7  mov     r12, [r12+8]
0x1800040cc  test    r12, r12
0x1800040cf  jz      loc_1800041CD
0x1800040d5  mov     rcx, r12; unsigned __int16 *
0x1800040d8  call    ?CbBstr@@YAKPEBG@Z; CbBstr(ushort const *)
0x1800040dd  mov     r13d, eax
0x1800040e0  mov     ecx, 1E0h; Size
0x1800040e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800040ea  test    rax, rax
0x1800040ed  jz      short loc_1800040FA
0x1800040ef  mov     rcx, rax; this
0x1800040f2  call    ??0RegExpExec@@QEAA@XZ; RegExpExec::RegExpExec(void)
0x1800040f7  mov     r15, rax
0x1800040fa  xor     eax, eax
0x1800040fc  test    r15, r15
0x1800040ff  jz      loc_18000405E
0x180004105  mov     dword ptr [rsp+148h+var_120], eax; int
0x180004109  lea     rax, [rsp+148h+var_58]
0x180004111  mov     [rsp+148h+var_128], rax; struct VAR *
0x180004116  mov     r9d, r13d; int
0x180004119  mov     r8, r12; unsigned __int8 *
0x18000411c  mov     rdx, [r14+18h]; struct CSession *
0x180004120  call    ?GetString@RegExpExec@@QEAAJPEAVCSession@@PEAEJPEAVVAR@@H@Z; RegExpExec::GetString(CSession *,uchar *,long,VAR *,int)
0x180004125  mov     ebx, eax
0x180004127  test    eax, eax
0x180004129  js      loc_1800041B4
0x18000412f  mov     dword ptr [rsp+148h+var_120], 1; int
0x180004137  lea     rax, [rsp+148h+var_40]
0x18000413f  mov     [rsp+148h+var_128], rax; struct VAR *
0x180004144  mov     r9d, r13d; int
0x180004147  mov     r8, r12; unsigned __int8 *
0x18000414a  mov     rdx, [r14+18h]; struct CSession *
0x18000414e  call    ?GetString@RegExpExec@@QEAAJPEAVCSession@@PEAEJPEAVVAR@@H@Z; RegExpExec::GetString(CSession *,uchar *,long,VAR *,int)
0x180004153  mov     ebx, eax
0x180004155  test    eax, eax
0x180004157  js      short loc_1800041B4
0x180004159  mov     rax, [rsp+148h+var_50]
0x180004161  mov     r12, [rax+8]
0x180004165  mov     [rsp+148h+var_E0], r12
0x18000416a  mov     rcx, r12; pbstr
0x18000416d  call    cs:__imp_SysStringLen
0x180004174  nop     dword ptr [rax+rax+00h]
0x180004179  mov     [rsp+148h+arg_18], eax
0x180004180  mov     [rsp+148h+var_F8], eax
0x180004184  mov     rcx, [rsp+148h+var_38]
0x18000418c  mov     r13, [rcx+8]
0x180004190  mov     [rsp+148h+var_D8], r13
0x180004195  mov     rcx, r13; pbstr
0x180004198  call    cs:__imp_SysStringLen
0x18000419f  nop     dword ptr [rax+rax+00h]
0x1800041a4  mov     ebx, eax
0x1800041a6  mov     [rsp+148h+var_F0], eax
0x1800041aa  mov     rcx, r15; this
0x1800041ad  call    ??_GRegExpExec@@QEAAPEAXI@Z; RegExpExec::`scalar deleting destructor'(uint)
0x1800041b2  jmp     short loc_1800041D4
0x1800041b4  mov     rcx, r15; this
0x1800041b7  call    ??_GRegExpExec@@QEAAPEAXI@Z; RegExpExec::`scalar deleting destructor'(uint)
0x1800041bc  mov     rax, [rdi]
0x1800041bf  mov     rcx, rdi
0x1800041c2  mov     rax, [rax+10h]
0x1800041c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041cb  jmp     short loc_1800041EB
0x1800041cd  lea     r12, String
0x1800041d4  mov     rax, [rdi]
0x1800041d7  mov     rcx, rdi
0x1800041da  mov     rax, [rax+10h]
0x1800041de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e3  xor     r15d, r15d
0x1800041e6  jmp     loc_180003F69
0x1800041eb  mov     rcx, [rsp+148h+Src]; Block
0x1800041f0  call    cs:__imp_free
0x1800041f7  nop     dword ptr [rax+rax+00h]
0x1800041fc  test    rsi, rsi
0x1800041ff  jnz     short loc_180004247
0x180004201  mov     rax, [rsp+148h+var_C0]
0x180004209  test    rax, rax
0x18000420c  jz      short loc_180004214
0x18000420e  test    byte ptr [rax+0Ch], 8
0x180004212  jz      short loc_180004259
0x180004214  mov     rax, [rsp+148h+var_88]
0x18000421c  test    rax, rax
0x18000421f  jz      short loc_180004227
0x180004221  test    byte ptr [rax+0Ch], 8
0x180004225  jz      short loc_180004268
0x180004227  mov     eax, ebx
0x180004229  lea     r11, [rsp+148h+var_28]
0x180004231  mov     rbx, [r11+30h]
0x180004235  mov     rsi, [r11+38h]
0x180004239  mov     rsp, r11
0x18000423c  pop     r15
0x18000423e  pop     r14
0x180004240  pop     r13
0x180004242  pop     r12
0x180004244  pop     rdi
0x180004245  retn
0x180004247  mov     rcx, rsi; this
0x18000424a  call    ??1RegExpComp@@QEAA@XZ; RegExpComp::~RegExpComp(void)
0x18000424f  mov     rcx, rsi; Block
0x180004252  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004257  jmp     short loc_180004201
0x180004259  lea     rcx, [rsp+148h+var_C8]; this
0x180004261  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x180004266  jmp     short loc_180004214
0x180004268  lea     rcx, [rsp+148h+var_90]; this
0x180004270  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x180004275  jmp     short loc_180004227
0x1800968b0  push    rbp
0x1800968b2  sub     rsp, 40h
0x1800968b6  mov     rbp, rdx
0x1800968b9  movzx   eax, cl
0x1800968bc  test    cl, cl
0x1800968be  jz      short loc_1800968FA
0x1800968c0  lea     rcx, [rbp+80h]; this
0x1800968c7  call    ?FDead@IScavengerBase@@QEAAHXZ; IScavengerBase::FDead(void)
0x1800968cc  test    eax, eax
0x1800968ce  jnz     short loc_1800968DD
0x1800968d0  lea     rcx, [rbp+80h]; this
0x1800968d7  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x1800968dc  nop
0x1800968dd  lea     rcx, [rbp+0B8h]; this
0x1800968e4  call    ?FDead@IScavengerBase@@QEAAHXZ; IScavengerBase::FDead(void)
0x1800968e9  test    eax, eax
0x1800968eb  jnz     short loc_1800968FA
0x1800968ed  lea     rcx, [rbp+0B8h]; this
0x1800968f4  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x1800968f9  nop
0x1800968fa  add     rsp, 40h
0x1800968fe  pop     rbp
0x1800968ff  retn
```
