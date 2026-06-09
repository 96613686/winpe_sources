# HyperVStorage::GetVariantValue(ushort const *,tagVARIANT &)

- ea: `0x180073ed8`
- end: `0x180074189`
- name: `?GetVariantValue@HyperVStorage@@QEBAJPEBGAEAUtagVARIANT@@@Z`
- size: `689`
- prototype: `int(HyperVStorage *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180096260`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x1800737e8`
- `0x180073ca8`
- `0x180073ed8`
- `0x180082244`
- `0x18008d3b0`
- `0x18008d87c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180073f21`
- `OLEAUT32!__imp_VariantInit` at `0x180073f21`
- `OLEAUT32!__imp_VariantClear` at `0x180074138`
- `OLEAUT32!__imp_VariantClear` at `0x180074138`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007402d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007402d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007412b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007412b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18007405d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18007405d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180074003`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180074003`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall HyperVStorage::GetVariantValue(
        HyperVStorage *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  HyperVStorageKeyTableEntry *v7; // r8
  __int64 v8; // rdx
  unsigned int v9; // ebx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  ULONG ValueSizeInBytes; // eax
  SAFEARRAY *Vector; // rax
  UINT FileObjectDataSizeInBytes; // eax
  BSTR v14; // rax
  __int64 v15; // r9
  int v16; // ebx
  __int16 v17; // ax
  UINT v18; // [rsp+40h] [rbp-78h] BYREF
  __int64 v19; // [rsp+48h] [rbp-70h] BYREF
  HyperVStorageKeyTableEntry *v20; // [rsp+50h] [rbp-68h]
  HyperVStorage *v21; // [rsp+58h] [rbp-60h]
  struct tagVARIANT *v22; // [rsp+60h] [rbp-58h]
  void *ppvData; // [rsp+70h] [rbp-48h] BYREF
  int v24; // [rsp+78h] [rbp-40h] BYREF

  v21 = this;
  v22 = a3;
  if ( !a2 )
    HvsThrowHResultError(-2147024809);
  VariantInit(a3);
  v19 = 0;
  if ( !(unsigned int)HyperVStorage::GetOrCreateNode(this, a2, 0, &v19, 0) )
    return 2147942402LL;
  v24 = 0;
  ppvData = 0;
  v7 = *(HyperVStorageKeyTableEntry **)(v19 + 40);
  v20 = v7;
  v8 = *(_QWORD *)v7;
  LODWORD(v19) = **(unsigned __int8 **)v7;
  switch ( (_DWORD)v19 )
  {
    case 3:
      a3->vt = 20;
      goto LABEL_23;
    case 4:
      a3->vt = 21;
      goto LABEL_23;
    case 5:
      a3->vt = 5;
LABEL_23:
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
      ppvData = &a3->decVal.8;
      v9 = 8;
      goto LABEL_24;
    case 6:
      if ( (*(_BYTE *)(v8 + 1) & 1) != 0 )
        FileObjectDataSizeInBytes = HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(v7);
      else
        FileObjectDataSizeInBytes = HyperVStorageKeyTableEntry::GetValueSizeInBytes(v7);
      v9 = FileObjectDataSizeInBytes;
      v18 = FileObjectDataSizeInBytes;
      v14 = SysAllocStringByteLen(0, FileObjectDataSizeInBytes);
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
      a3->llVal = (LONGLONG)v14;
      ppvData = v14;
      memset_0(v14, 0, v9 + 2LL);
      a3->vt = 8;
      goto LABEL_25;
    case 7:
      if ( (*(_BYTE *)(v8 + 1) & 1) != 0 )
        ValueSizeInBytes = HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(v7);
      else
        ValueSizeInBytes = HyperVStorageKeyTableEntry::GetValueSizeInBytes(v7);
      v9 = ValueSizeInBytes;
      v18 = ValueSizeInBytes;
      Vector = SafeArrayCreateVector(0x11u, 0, ValueSizeInBytes);
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
      a3->llVal = (LONGLONG)Vector;
      if ( !Vector )
        HvsThrowHResultError(-2147024882);
      a3->vt = 8209;
      SafeArrayAccessData(Vector, &ppvData);
      goto LABEL_25;
  }
  if ( (_DWORD)v19 != 8 )
    HvsThrowHResultError(-2147024809);
  ppvData = &v24;
  v9 = 4;
  a3->vt = 11;
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a3->llVal;
LABEL_24:
  v18 = v9;
LABEL_25:
  v15 = v9;
  v16 = v19;
  HyperVStorage::GetValueInternal(v21, v20, (unsigned int)v19, v15, ppvData, &v18, 0);
  if ( v16 == 8 )
  {
    if ( v24 )
      v17 = -1;
    else
      v17 = 0;
    p_llVal->iVal = v17;
  }
  if ( a3->vt == 8209 )
    SafeArrayUnaccessData(p_llVal->parray);
  return 0;
}

```

## disassembly

```asm
0x180073ed8  mov     [rsp+arg_18], rbx
0x180073edd  push    rsi
0x180073ede  push    r12
0x180073ee0  push    r13
0x180073ee2  push    r14
0x180073ee4  push    r15
0x180073ee6  sub     rsp, 90h
0x180073eed  mov     rax, cs:__security_cookie
0x180073ef4  xor     rax, rsp
0x180073ef7  mov     [rsp+0B8h+var_38], rax
0x180073eff  mov     r12, r8
0x180073f02  mov     rbx, rdx
0x180073f05  mov     rsi, rcx
0x180073f08  mov     [rsp+0B8h+var_60], rcx
0x180073f0d  mov     r14, r8
0x180073f10  mov     [rsp+0B8h+var_58], r8
0x180073f15  test    rdx, rdx
0x180073f18  jz      loc_180074169
0x180073f1e  mov     rcx, r12; pvarg
0x180073f21  call    cs:__imp_VariantInit
0x180073f27  mov     [rsp+0B8h+var_70], 0
0x180073f30  mov     [rsp+0B8h+var_88], 0
0x180073f35  mov     [rsp+0B8h+var_98], 0
0x180073f3e  lea     r9, [rsp+0B8h+var_70]
0x180073f43  xor     r8d, r8d
0x180073f46  mov     rdx, rbx
0x180073f49  mov     rcx, rsi
0x180073f4c  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x180073f51  test    eax, eax
0x180073f53  jnz     short loc_180073F5F
0x180073f55  mov     eax, 80070002h
0x180073f5a  jmp     loc_180074140
0x180073f5f  mov     [rsp+0B8h+var_40], 0
0x180073f67  mov     [rsp+0B8h+ppvData], 0
0x180073f70  mov     rax, [rsp+0B8h+var_70]
0x180073f75  mov     r8, [rax+28h]
0x180073f79  mov     [rsp+0B8h+var_68], r8
0x180073f7e  mov     rdx, [r8]
0x180073f81  movzx   ecx, byte ptr [rdx]
0x180073f84  mov     dword ptr [rsp+0B8h+var_70], ecx
0x180073f88  sub     ecx, 3
0x180073f8b  jz      loc_1800740A0
0x180073f91  sub     ecx, 1
0x180073f94  jz      loc_180074097
0x180073f9a  sub     ecx, 1
0x180073f9d  jz      loc_18007408E
0x180073fa3  sub     ecx, 1
0x180073fa6  jz      loc_18007403E
0x180073fac  sub     ecx, 1
0x180073faf  jz      short loc_180073FDE
0x180073fb1  cmp     ecx, 1
0x180073fb4  jnz     loc_180074173
0x180073fba  lea     rax, [rsp+0B8h+var_40]
0x180073fbf  mov     [rsp+0B8h+ppvData], rax
0x180073fc4  mov     ebx, 4
0x180073fc9  mov     word ptr [r12], 0Bh
0x180073fd0  lea     rsi, [r12+8]
0x180073fd5  lea     r15d, [rbx+4]
0x180073fd9  jmp     loc_1800740BA
0x180073fde  mov     rcx, r8; this
0x180073fe1  test    byte ptr [rdx+1], 1
0x180073fe5  jnz     short loc_180073FEE
0x180073fe7  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x180073fec  jmp     short loc_180073FF3
0x180073fee  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x180073ff3  mov     ebx, eax
0x180073ff5  mov     [rsp+0B8h+var_78], eax
0x180073ff9  mov     ecx, 11h; vt
0x180073ffe  mov     r8d, eax; cElements
0x180074001  xor     edx, edx; lLbound
0x180074003  call    cs:__imp_SafeArrayCreateVector
0x180074009  lea     rsi, [r12+8]
0x18007400e  mov     [rsi], rax
0x180074011  test    rax, rax
0x180074014  jz      loc_18007417D
0x18007401a  mov     r13d, 2011h
0x180074020  mov     [r12], r13w
0x180074025  lea     rdx, [rsp+0B8h+ppvData]; ppvData
0x18007402a  mov     rcx, rax; psa
0x18007402d  call    cs:__imp_SafeArrayAccessData
0x180074033  mov     r15d, 8
0x180074039  jmp     loc_1800740C4
0x18007403e  mov     rcx, r8; this
0x180074041  test    byte ptr [rdx+1], 1
0x180074045  jnz     short loc_18007404E
0x180074047  call    ?GetValueSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetValueSizeInBytes(void)
0x18007404c  jmp     short loc_180074053
0x18007404e  call    ?GetFileObjectDataSizeInBytes@HyperVStorageKeyTableEntry@@QEBAIXZ; HyperVStorageKeyTableEntry::GetFileObjectDataSizeInBytes(void)
0x180074053  mov     ebx, eax
0x180074055  mov     [rsp+0B8h+var_78], eax
0x180074059  mov     edx, eax; len
0x18007405b  xor     ecx, ecx; psz
0x18007405d  call    cs:__imp_SysAllocStringByteLen
0x180074063  lea     rsi, [r12+8]
0x180074068  mov     [rsi], rax
0x18007406b  mov     [rsp+0B8h+ppvData], rax
0x180074070  mov     r8d, ebx
0x180074073  add     r8, 2; Size
0x180074077  xor     edx, edx; Val
0x180074079  mov     rcx, rax; void *
0x18007407c  call    memset_0
0x180074081  mov     r15d, 8
0x180074087  mov     [r12], r15w
0x18007408c  jmp     short loc_1800740BE
0x18007408e  mov     word ptr [r12], 5
0x180074095  jmp     short loc_1800740A7
0x180074097  mov     word ptr [r12], 15h
0x18007409e  jmp     short loc_1800740A7
0x1800740a0  mov     word ptr [r12], 14h
0x1800740a7  lea     rsi, [r12+8]
0x1800740ac  mov     r15d, 8
0x1800740b2  mov     [rsp+0B8h+ppvData], rsi
0x1800740b7  mov     ebx, r15d
0x1800740ba  mov     [rsp+0B8h+var_78], ebx
0x1800740be  mov     r13d, 2011h
0x1800740c4  lea     rax, [rsp+0B8h+var_78]
0x1800740c9  mov     [rsp+0B8h+var_90], rax
0x1800740ce  mov     rax, [rsp+0B8h+ppvData]
0x1800740d3  mov     [rsp+0B8h+var_98], rax
0x1800740d8  mov     r9d, ebx
0x1800740db  mov     ebx, dword ptr [rsp+0B8h+var_70]
0x1800740df  mov     r8d, ebx
0x1800740e2  mov     rdx, [rsp+0B8h+var_68]
0x1800740e7  mov     rcx, [rsp+0B8h+var_60]
0x1800740ec  call    ?GetValueInternal@HyperVStorage@@IEBAXPEBVHyperVStorageKeyTableEntry@@W4HyperVStorageKeyType@@IPEAEAEAI@Z; HyperVStorage::GetValueInternal(HyperVStorageKeyTableEntry const *,HyperVStorageKeyType,uint,uchar *,uint &)
0x1800740f1  cmp     ebx, r15d
0x1800740f4  jnz     short loc_180074107
0x1800740f6  cmp     [rsp+0B8h+var_40], 0
0x1800740fb  jz      short loc_180074102
0x1800740fd  or      eax, 0FFFFFFFFh
0x180074100  jmp     short loc_180074104
0x180074102  xor     eax, eax
0x180074104  mov     [rsi], ax
0x180074107  xor     ebx, ebx
0x180074109  jmp     short loc_180074121
0x18007410b  mov     r14, [rsp+0B8h+var_58]
0x180074110  lea     rsi, [r14+8]
0x180074114  mov     r13d, 2011h
0x18007411a  mov     ebx, dword ptr [rsp+0B8h+var_70]
0x18007411e  mov     r12, r14
0x180074121  cmp     [r12], r13w
0x180074126  jnz     short loc_180074131
0x180074128  mov     rcx, [rsi]; psa
0x18007412b  call    cs:__imp_SafeArrayUnaccessData
0x180074131  test    ebx, ebx
0x180074133  jns     short loc_18007413E
0x180074135  mov     rcx, r14; pvarg
0x180074138  call    cs:__imp_VariantClear
0x18007413e  mov     eax, ebx
0x180074140  mov     rcx, [rsp+0B8h+var_38]
0x180074148  xor     rcx, rsp; StackCookie
0x18007414b  call    __security_check_cookie
0x180074150  mov     rbx, [rsp+0B8h+arg_18]
0x180074158  add     rsp, 90h
0x18007415f  pop     r15
0x180074161  pop     r14
0x180074163  pop     r13
0x180074165  pop     r12
0x180074167  pop     rsi
0x180074168  retn
0x180074169  mov     ecx, 80070057h; int
0x18007416e  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x180074173  mov     ecx, 80070057h; int
0x180074178  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
0x18007417d  mov     ecx, 8007000Eh; int
0x180074182  call    ?HvsThrowHResultError@@YAXJ@Z; HvsThrowHResultError(long)
```
