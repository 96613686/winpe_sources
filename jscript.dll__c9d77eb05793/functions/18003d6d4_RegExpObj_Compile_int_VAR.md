# RegExpObj::Compile(int,VAR *)

- ea: `0x18003d6d4`
- end: `0x18003db1c`
- name: `?Compile@RegExpObj@@QEAAJHPEAVVAR@@@Z`
- size: `1096`
- prototype: `__int64 __fastcall(RegExpObj *__hidden this, int, struct VAR *)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043a80`
- `0x180043c14`
- `0x18006f6b0`

## callees

- `0x180006df0`
- `0x1800079fc`
- `0x1800082fc`
- `0x18000ad6c`
- `0x18000bf44`
- `0x18000e788`
- `0x18003d61c`
- `0x18003d688`
- `0x18003d6d4`
- `0x18003db24`
- `0x18003dee4`
- `0x180049d84`
- `0x18004d188`
- `0x180057694`
- `0x1800576a0`
- `0x18006e544`
- `0x180086798`
- `0x180094282`
- `0x180096010`

## import_xrefs

- `msvcrt!free` at `0x18003da9c`
- `msvcrt!free` at `0x18003da9c`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d7a3`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d819`
- `OLEAUT32!__imp_SysStringLen` at `0x18003da25`
- `OLEAUT32!__imp_SysStringLen` at `0x18003da4a`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d7a3`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d819`
- `OLEAUT32!__imp_SysStringLen` at `0x18003da25`
- `OLEAUT32!__imp_SysStringLen` at `0x18003da4a`

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
  _BYTE v37[24]; // [rsp+A0h] [rbp-A8h] BYREF
  _BYTE v38[8]; // [rsp+B8h] [rbp-90h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-88h]
  _BYTE v40[24]; // [rsp+D8h] [rbp-70h] BYREF
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
      String = ConvertToString(this[3], &v27, (struct VAR *)v37, 1);
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
        String = ConvertToString(this[3], &v27, (struct VAR *)v40, 1);
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
0x18003d6d4  mov     rax, rsp
0x18003d6d7  mov     [rax+8], rbx
0x18003d6db  mov     [rax+10h], rsi
0x18003d6df  mov     [rax+18h], r8
0x18003d6e3  push    rdi
0x18003d6e4  push    r12
0x18003d6e6  push    r13
0x18003d6e8  push    r14
0x18003d6ea  push    r15
0x18003d6ec  sub     rsp, 120h
0x18003d6f3  mov     rdi, r8
0x18003d6f6  movsxd  r15, edx
0x18003d6f9  mov     r14, rcx
0x18003d6fc  xor     ebx, ebx
0x18003d6fe  mov     esi, ebx
0x18003d700  mov     [rsp+148h+Src], rbx
0x18003d705  mov     [rsp+148h+len], ebx
0x18003d709  lea     rcx, [rax-0C8h]; this
0x18003d710  call    ??0ScavVariant@@QEAA@XZ; ScavVariant::ScavVariant(void)
0x18003d715  lea     rcx, [rsp+148h+var_90]; this
0x18003d71d  call    ??0ScavVariant@@QEAA@XZ; ScavVariant::ScavVariant(void)
0x18003d722  lea     r12, String
0x18003d729  mov     r13, r12
0x18003d72c  mov     [rsp+148h+arg_18], ebx
0x18003d733  mov     [rsp+148h+var_F4], ebx
0x18003d737  test    r15d, r15d
0x18003d73a  jle     loc_18003DA8F
0x18003d740  lea     rax, [r15-1]
0x18003d744  lea     rcx, [rax+rax*2]
0x18003d748  lea     rcx, [rdi+rcx*8]; struct VAR *
0x18003d74c  mov     [rsp+148h+var_100], rcx
0x18003d751  call    ?GetRegExp@@YAPEAVRegExpObj@@PEAVVAR@@@Z; GetRegExp(VAR *)
0x18003d756  mov     rdi, rax
0x18003d759  xor     ecx, ecx
0x18003d75b  test    rax, rax
0x18003d75e  jnz     loc_18003D924
0x18003d764  mov     rax, [rsp+148h+var_100]
0x18003d769  cmp     [rax], cx
0x18003d76c  jz      short loc_18003D7B8
0x18003d76e  lea     r9d, [rbx+1]; int
0x18003d772  lea     r8, [rsp+148h+var_A8]; struct VAR *
0x18003d77a  lea     rdx, [rsp+148h+var_100]; struct VAR **
0x18003d77f  mov     rcx, [r14+18h]; struct CSession *
0x18003d783  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18003d788  mov     ebx, eax
0x18003d78a  test    eax, eax
0x18003d78c  js      loc_18003DA97
0x18003d792  mov     rax, [rsp+148h+var_100]
0x18003d797  mov     r12, [rax+8]
0x18003d79b  mov     [rsp+148h+var_E0], r12
0x18003d7a0  mov     rcx, r12; pbstr
0x18003d7a3  call    cs:__imp_SysStringLen
0x18003d7a9  mov     [rsp+148h+arg_18], eax
0x18003d7b0  mov     [rsp+148h+var_F8], eax
0x18003d7b4  mov     ebx, [rsp+148h+var_F4]
0x18003d7b8  cmp     r15d, 2
0x18003d7bc  jl      loc_18003DA8F
0x18003d7c2  lea     rax, [r15-2]
0x18003d7c6  lea     rax, [rax+rax*2]
0x18003d7ca  mov     rcx, [rsp+148h+arg_10]
0x18003d7d2  lea     rcx, [rcx+rax*8]
0x18003d7d6  mov     [rsp+148h+var_100], rcx
0x18003d7db  xor     r15d, r15d
0x18003d7de  cmp     [rcx], r15w
0x18003d7e2  jz      short loc_18003D825
0x18003d7e4  lea     r9d, [r15+1]; int
0x18003d7e8  lea     r8, [rsp+148h+var_70]; struct VAR *
0x18003d7f0  lea     rdx, [rsp+148h+var_100]; struct VAR **
0x18003d7f5  mov     rcx, [r14+18h]; struct CSession *
0x18003d7f9  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x18003d7fe  mov     ebx, eax
0x18003d800  test    eax, eax
0x18003d802  js      loc_18003DA97
0x18003d808  mov     rax, [rsp+148h+var_100]
0x18003d80d  mov     r13, [rax+8]
0x18003d811  mov     [rsp+148h+var_D8], r13
0x18003d816  mov     rcx, r13; pbstr
0x18003d819  call    cs:__imp_SysStringLen
0x18003d81f  mov     ebx, eax
0x18003d821  mov     [rsp+148h+var_F0], eax
0x18003d825  mov     edi, 80h
0x18003d82a  mov     ecx, 160h; Size
0x18003d82f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d834  test    rax, rax
0x18003d837  jz      loc_18003D912
0x18003d83d  mov     rcx, rax; this
0x18003d840  call    ??0RegExpComp@@QEAA@XZ; RegExpComp::RegExpComp(void)
0x18003d845  mov     rsi, rax
0x18003d848  mov     [rsp+148h+var_D0], rsi
0x18003d84d  test    rsi, rsi
0x18003d850  jz      loc_18003D91A
0x18003d856  lea     rax, [rsp+148h+len]
0x18003d85b  mov     [rsp+148h+var_118], rax; int *
0x18003d860  lea     rax, [rsp+148h+Src]
0x18003d865  mov     [rsp+148h+var_120], rax; unsigned __int8 **
0x18003d86a  mov     dword ptr [rsp+148h+var_128], ebx; int
0x18003d86e  mov     r9, r13; unsigned __int16 *
0x18003d871  mov     r8d, [rsp+148h+arg_18]; int
0x18003d879  mov     rdx, r12; unsigned __int16 *
0x18003d87c  mov     rcx, rsi; this
0x18003d87f  call    ?CompileDynamic@RegExpComp@@QEAAJPEBGJ0JPEAPEAEPEAJ@Z; RegExpComp::CompileDynamic(ushort const *,long,ushort const *,long,uchar * *,long *)
0x18003d884  mov     ebx, eax
0x18003d886  test    eax, eax
0x18003d888  js      loc_18003DA97
0x18003d88e  mov     rdx, [r14+18h]; struct CSession *
0x18003d892  mov     ecx, [rsp+148h+len]; len
0x18003d896  call    ?PvarAllocBstrByteLen@@YAPEAVVAR@@JPEAVCSession@@@Z; PvarAllocBstrByteLen(long,CSession *)
0x18003d89b  mov     rbx, rax
0x18003d89e  test    rax, rax
0x18003d8a1  jz      short loc_18003D91A
0x18003d8a3  movsxd  r8, [rsp+148h+len]; Size
0x18003d8a8  mov     rdx, [rsp+148h+Src]; Src
0x18003d8ad  mov     rcx, [rax+8]; void *
0x18003d8b1  call    memcpy_0
0x18003d8b6  mov     [r14+68h], di
0x18003d8bb  mov     [r14+70h], rbx
0x18003d8bf  mov     [r14+80h], r15w
0x18003d8c7  mov     [r14+98h], r15w
0x18003d8cf  mov     [r14+0B0h], r15w
0x18003d8d7  mov     [r14+0C8h], r15w
0x18003d8df  mov     [r14+0E0h], r15w
0x18003d8e7  mov     [r14+0F8h], r15w
0x18003d8ef  mov     eax, 3
0x18003d8f4  mov     [r14+110h], ax
0x18003d8fc  mov     [r14+118h], r15d
0x18003d903  mov     [r14+128h], r15d
0x18003d90a  mov     ebx, r15d
0x18003d90d  jmp     loc_18003DA97
0x18003d912  mov     rsi, r15
0x18003d915  jmp     loc_18003D848
0x18003d91a  mov     ebx, 8007000Eh
0x18003d91f  jmp     loc_18003DA97
0x18003d924  cmp     r15d, 2
0x18003d928  jl      short loc_18003D95D
0x18003d92a  lea     rax, [r15-2]
0x18003d92e  lea     rax, [rax+rax*2]
0x18003d932  mov     rcx, [rsp+148h+arg_10]
0x18003d93a  xor     r15d, r15d
0x18003d93d  cmp     [rcx+rax*8], r15w
0x18003d942  jz      short loc_18003D960
0x18003d944  mov     rax, [rdi]
0x18003d947  mov     rcx, rdi
0x18003d94a  mov     rax, [rax+10h]
0x18003d94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d953  mov     ebx, 800A1399h
0x18003d958  jmp     loc_18003DA97
0x18003d95d  xor     r15d, r15d
0x18003d960  mov     eax, 80h
0x18003d965  cmp     ax, [rdi+68h]
0x18003d969  jnz     loc_18003DA80
0x18003d96f  mov     r12, [rdi+70h]
0x18003d973  mov     rcx, r12; this
0x18003d976  call    ?FBstr@VAR@@QEAAHXZ; VAR::FBstr(void)
0x18003d97b  test    eax, eax
0x18003d97d  jz      loc_18003DA79
0x18003d983  mov     r12, [r12+8]
0x18003d988  test    r12, r12
0x18003d98b  jz      loc_18003DA79
0x18003d991  mov     rcx, r12; unsigned __int16 *
0x18003d994  call    ?CbBstr@@YAKPEBG@Z; CbBstr(ushort const *)
0x18003d999  mov     r13d, eax
0x18003d99c  mov     ecx, 1E0h; Size
0x18003d9a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d9a6  test    rax, rax
0x18003d9a9  jz      short loc_18003D9B6
0x18003d9ab  mov     rcx, rax; this
0x18003d9ae  call    ??0RegExpExec@@QEAA@XZ; RegExpExec::RegExpExec(void)
0x18003d9b3  mov     r15, rax
0x18003d9b6  xor     eax, eax
0x18003d9b8  test    r15, r15
0x18003d9bb  jz      loc_18003D91A
0x18003d9c1  mov     dword ptr [rsp+148h+var_120], eax; int
0x18003d9c5  lea     rax, [rsp+148h+var_58]
0x18003d9cd  mov     [rsp+148h+var_128], rax; struct VAR *
0x18003d9d2  mov     r9d, r13d; int
0x18003d9d5  mov     r8, r12; unsigned __int8 *
0x18003d9d8  mov     rdx, [r14+18h]; struct CSession *
0x18003d9dc  call    ?GetString@RegExpExec@@QEAAJPEAVCSession@@PEAEJPEAVVAR@@H@Z; RegExpExec::GetString(CSession *,uchar *,long,VAR *,int)
0x18003d9e1  mov     ebx, eax
0x18003d9e3  test    eax, eax
0x18003d9e5  js      short loc_18003DA60
0x18003d9e7  mov     dword ptr [rsp+148h+var_120], 1; int
0x18003d9ef  lea     rax, [rsp+148h+var_40]
0x18003d9f7  mov     [rsp+148h+var_128], rax; struct VAR *
0x18003d9fc  mov     r9d, r13d; int
0x18003d9ff  mov     r8, r12; unsigned __int8 *
0x18003da02  mov     rdx, [r14+18h]; struct CSession *
0x18003da06  call    ?GetString@RegExpExec@@QEAAJPEAVCSession@@PEAEJPEAVVAR@@H@Z; RegExpExec::GetString(CSession *,uchar *,long,VAR *,int)
0x18003da0b  mov     ebx, eax
0x18003da0d  test    eax, eax
0x18003da0f  js      short loc_18003DA60
0x18003da11  mov     rax, [rsp+148h+var_50]
0x18003da19  mov     r12, [rax+8]
0x18003da1d  mov     [rsp+148h+var_E0], r12
0x18003da22  mov     rcx, r12; pbstr
0x18003da25  call    cs:__imp_SysStringLen
0x18003da2b  mov     [rsp+148h+arg_18], eax
0x18003da32  mov     [rsp+148h+var_F8], eax
0x18003da36  mov     rcx, [rsp+148h+var_38]
0x18003da3e  mov     r13, [rcx+8]
0x18003da42  mov     [rsp+148h+var_D8], r13
0x18003da47  mov     rcx, r13; pbstr
0x18003da4a  call    cs:__imp_SysStringLen
0x18003da50  mov     ebx, eax
0x18003da52  mov     [rsp+148h+var_F0], eax
0x18003da56  mov     rcx, r15; this
0x18003da59  call    ??_GRegExpExec@@QEAAPEAXI@Z; RegExpExec::`scalar deleting destructor'(uint)
0x18003da5e  jmp     short loc_18003DA80
0x18003da60  mov     rcx, r15; this
0x18003da63  call    ??_GRegExpExec@@QEAAPEAXI@Z; RegExpExec::`scalar deleting destructor'(uint)
0x18003da68  mov     rax, [rdi]
0x18003da6b  mov     rcx, rdi
0x18003da6e  mov     rax, [rax+10h]
0x18003da72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da77  jmp     short loc_18003DA97
0x18003da79  lea     r12, String
0x18003da80  mov     rax, [rdi]
0x18003da83  mov     rcx, rdi
0x18003da86  mov     rax, [rax+10h]
0x18003da8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da8f  xor     r15d, r15d
0x18003da92  jmp     loc_18003D825
0x18003da97  mov     rcx, [rsp+148h+Src]; Block
0x18003da9c  call    cs:__imp_free
0x18003daa2  test    rsi, rsi
0x18003daa5  jnz     short loc_18003DAEC
0x18003daa7  mov     rax, [rsp+148h+var_C0]
0x18003daaf  test    rax, rax
0x18003dab2  jz      short loc_18003DABA
0x18003dab4  test    byte ptr [rax+0Ch], 8
0x18003dab8  jz      short loc_18003DAFE
0x18003daba  mov     rax, [rsp+148h+var_88]
0x18003dac2  test    rax, rax
0x18003dac5  jz      short loc_18003DACD
0x18003dac7  test    byte ptr [rax+0Ch], 8
0x18003dacb  jz      short loc_18003DB0D
0x18003dacd  mov     eax, ebx
0x18003dacf  lea     r11, [rsp+148h+var_28]
0x18003dad7  mov     rbx, [r11+30h]
0x18003dadb  mov     rsi, [r11+38h]
0x18003dadf  mov     rsp, r11
0x18003dae2  pop     r15
0x18003dae4  pop     r14
0x18003dae6  pop     r13
0x18003dae8  pop     r12
0x18003daea  pop     rdi
0x18003daeb  retn
0x18003daec  mov     rcx, rsi; this
0x18003daef  call    ??1RegExpComp@@QEAA@XZ; RegExpComp::~RegExpComp(void)
0x18003daf4  mov     rcx, rsi; Block
0x18003daf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003dafc  jmp     short loc_18003DAA7
0x18003dafe  lea     rcx, [rsp+148h+var_C8]; this
0x18003db06  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x18003db0b  jmp     short loc_18003DABA
0x18003db0d  lea     rcx, [rsp+148h+var_90]; this
0x18003db15  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x18003db1a  jmp     short loc_18003DACD
0x18009484e  push    rbp
0x180094850  sub     rsp, 40h
0x180094854  mov     rbp, rdx
0x180094857  movzx   eax, cl
0x18009485a  test    cl, cl
0x18009485c  jz      short loc_180094898
0x18009485e  lea     rcx, [rbp+80h]; this
0x180094865  call    ?FDead@IScavengerBase@@QEAAHXZ; IScavengerBase::FDead(void)
0x18009486a  test    eax, eax
0x18009486c  jnz     short loc_18009487B
0x18009486e  lea     rcx, [rbp+80h]; this
0x180094875  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x18009487a  nop
0x18009487b  lea     rcx, [rbp+0B8h]; this
0x180094882  call    ?FDead@IScavengerBase@@QEAAHXZ; IScavengerBase::FDead(void)
0x180094887  test    eax, eax
0x180094889  jnz     short loc_180094898
0x18009488b  lea     rcx, [rbp+0B8h]; this
0x180094892  call    ?Close@IScavengerBase@@QEAAXXZ; IScavengerBase::Close(void)
0x180094897  nop
0x180094898  add     rsp, 40h
0x18009489c  pop     rbp
0x18009489d  retn
```
