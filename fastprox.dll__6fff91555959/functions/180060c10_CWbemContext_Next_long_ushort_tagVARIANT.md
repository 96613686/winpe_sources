# CWbemContext::Next(long,ushort * *,tagVARIANT *)

- ea: `0x180060c10`
- end: `0x180060f29`
- name: `?Next@CWbemContext@@UEAAJJPEAPEAGPEAUtagVARIANT@@@Z`
- size: `793`
- prototype: `__int64 __fastcall(CWbemContext *__hidden this, int, unsigned __int16 **, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180037120`
- `0x180060c10`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180060c6e`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180060cb2`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180060ecd`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180060c6e`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180060cb2`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180060ecd`
- `wbemcomn!GetMemLogObject` at `0x180060d29`
- `wbemcomn!GetMemLogObject` at `0x180060d6e`
- `wbemcomn!GetMemLogObject` at `0x180060dbc`
- `wbemcomn!GetMemLogObject` at `0x180060e31`
- `wbemcomn!GetMemLogObject` at `0x180060e7c`
- `wbemcomn!GetMemLogObject` at `0x180060edd`
- `wbemcomn!GetMemLogObject` at `0x180060d29`
- `wbemcomn!GetMemLogObject` at `0x180060d6e`
- `wbemcomn!GetMemLogObject` at `0x180060dbc`
- `wbemcomn!GetMemLogObject` at `0x180060e31`
- `wbemcomn!GetMemLogObject` at `0x180060e7c`
- `wbemcomn!GetMemLogObject` at `0x180060edd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180060c5a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180060c5a`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180060d10`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180060d10`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180060c31`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180060c31`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060d39`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060d7e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060dcc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060e41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060e8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060eed`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060d39`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060d7e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060dcc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060e41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060e8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180060eed`
- `OLEAUT32!__imp_SysAllocString` at `0x180060c77`
- `OLEAUT32!__imp_SysAllocString` at `0x180060c77`
- `OLEAUT32!__imp_VariantInit` at `0x180060ca6`
- `OLEAUT32!__imp_VariantInit` at `0x180060ca6`
- `OLEAUT32!__imp_VariantCopy` at `0x180060cc1`
- `OLEAUT32!__imp_VariantCopy` at `0x180060cc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemContext::Next(CWbemContext *this, int a2, unsigned __int16 **a3, struct tagVARIANT *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // edx
  const OLECHAR **v10; // rax
  unsigned __int16 *v11; // rax
  char *v12; // rax
  HRESULT v13; // ebx
  CWbemRefreshingSvc *v14; // rcx
  CMemoryLog *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF
  char v25; // [rsp+70h] [rbp+8h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)&v25, (struct _RTL_CRITICAL_SECTION *)((char *)this + 168));
  if ( a2 )
  {
    MemLogObject = GetMemLogObject();
    v13 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_10;
    }
    v17 = 64;
    goto LABEL_20;
  }
  if ( !a3 )
  {
    v22 = GetMemLogObject();
    v13 = -2147217400;
    CMemoryLog::Write(v22, -2147217400);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_10;
    }
    v17 = 65;
    goto LABEL_20;
  }
  if ( *((_DWORD *)this + 7) == -1 )
  {
    v16 = GetMemLogObject();
    v13 = -2147217379;
    CMemoryLog::Write(v16, -2147217379);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_10;
    }
    v17 = 66;
    v18 = 2147749917LL;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v14 + 2), v17, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, v18);
    goto LABEL_10;
  }
  v8 = CFlexArray::Size((CWbemContext *)((char *)this + 40));
  v9 = *((_DWORD *)this + 7);
  if ( v9 >= v8 )
  {
    v13 = 262149;
    goto LABEL_10;
  }
  v10 = (const OLECHAR **)CFlexArray::GetAt((CWbemContext *)((char *)this + 40), v9);
  v11 = SysAllocString(*v10);
  *a3 = v11;
  if ( !v11 && *(_QWORD *)CFlexArray::GetAt((CWbemContext *)((char *)this + 40), *((_DWORD *)this + 7)) )
  {
    v23 = GetMemLogObject();
    v13 = -2147217402;
    CMemoryLog::Write(v23, -2147217402);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 67;
      goto LABEL_25;
    }
    goto LABEL_10;
  }
  if ( !a4 )
  {
    v19 = GetMemLogObject();
    v13 = -2147217400;
    CMemoryLog::Write(v19, -2147217400);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_10;
    }
    v17 = 68;
LABEL_20:
    v18 = 2147749896LL;
    goto LABEL_26;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v12 = (char *)CFlexArray::GetAt((CWbemContext *)((char *)this + 40), *((_DWORD *)this + 7));
  v13 = VariantCopy(&pvarg, (const VARIANTARG *)(v12 + 16));
  if ( v13 < 0 )
  {
    v20 = GetMemLogObject();
    v13 = -2147217402;
    CMemoryLog::Write(v20, -2147217402);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 69;
LABEL_25:
      v18 = 2147749894LL;
      goto LABEL_26;
    }
  }
  else
  {
    *a4 = pvarg;
    pvarg.vt = 0;
    ++*((_DWORD *)this + 7);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 70;
      v18 = (unsigned int)v13;
      goto LABEL_26;
    }
  }
LABEL_10:
  CInCritSec::~CInCritSec((CInCritSec *)&v25);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180060c10  push    rbx
0x180060c12  push    rsi
0x180060c13  push    rdi
0x180060c14  push    r14
0x180060c16  sub     rsp, 48h
0x180060c1a  mov     rsi, r9
0x180060c1d  mov     r14, r8
0x180060c20  mov     ebx, edx
0x180060c22  mov     rdi, rcx
0x180060c25  lea     rdx, [rcx+0A8h]
0x180060c2c  lea     rcx, [rsp+68h+arg_0]
0x180060c31  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180060c37  nop
0x180060c38  test    ebx, ebx
0x180060c3a  jnz     loc_180060E31
0x180060c40  test    r14, r14
0x180060c43  jz      loc_180060E7C
0x180060c49  cmp     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180060c4d  jz      loc_180060D29
0x180060c53  lea     rbx, [rdi+28h]
0x180060c57  mov     rcx, rbx
0x180060c5a  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180060c60  mov     edx, [rdi+1Ch]
0x180060c63  cmp     edx, eax
0x180060c65  jnb     loc_180060D22
0x180060c6b  mov     rcx, rbx
0x180060c6e  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180060c74  mov     rcx, [rax]; psz
0x180060c77  call    cs:__imp_SysAllocString
0x180060c7d  mov     [r14], rax
0x180060c80  test    rax, rax
0x180060c83  jz      loc_180060EC7
0x180060c89  test    rsi, rsi
0x180060c8c  jz      loc_180060D6E
0x180060c92  xorps   xmm0, xmm0
0x180060c95  xor     eax, eax
0x180060c97  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x180060c9c  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x180060ca1  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180060ca6  call    cs:__imp_VariantInit
0x180060cac  mov     edx, [rdi+1Ch]
0x180060caf  mov     rcx, rbx
0x180060cb2  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180060cb8  lea     rdx, [rax+10h]; pvargSrc
0x180060cbc  lea     rcx, [rsp+68h+pvarg]; pvargDest
0x180060cc1  call    cs:__imp_VariantCopy
0x180060cc7  mov     ebx, eax
0x180060cc9  test    eax, eax
0x180060ccb  js      loc_180060DBC
0x180060cd1  movups  xmm0, xmmword ptr [rsp+68h+pvarg]
0x180060cd6  movups  xmmword ptr [rsi], xmm0
0x180060cd9  movsd   xmm1, qword ptr [rsp+68h+pvarg+10h]
0x180060cdf  movsd   qword ptr [rsi+10h], xmm1
0x180060ce4  xor     ecx, ecx
0x180060ce6  mov     word ptr [rsp+68h+pvarg], cx
0x180060ceb  inc     dword ptr [rdi+1Ch]
0x180060cee  lea     rax, WPP_GLOBAL_Control
0x180060cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180060cfc  cmp     rcx, rax
0x180060cff  jz      short loc_180060D0B
0x180060d01  test    byte ptr [rcx+1Ch], 1
0x180060d05  jnz     loc_180060E1D
0x180060d0b  lea     rcx, [rsp+68h+arg_0]
0x180060d10  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x180060d16  mov     eax, ebx
0x180060d18  add     rsp, 48h
0x180060d1c  pop     r14
0x180060d1e  pop     rdi
0x180060d1f  pop     rsi
0x180060d20  pop     rbx
0x180060d21  retn
0x180060d22  mov     ebx, 40005h
0x180060d27  jmp     short loc_180060D0B
0x180060d29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060d2f  mov     ebx, 8004101Dh
0x180060d34  mov     edx, ebx
0x180060d36  mov     rcx, rax
0x180060d39  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060d3f  lea     rax, WPP_GLOBAL_Control
0x180060d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180060d4d  cmp     rcx, rax
0x180060d50  jz      short loc_180060D0B
0x180060d52  test    byte ptr [rcx+1Ch], 1
0x180060d56  jz      short loc_180060D0B
0x180060d58  cmp     byte ptr [rcx+19h], 2
0x180060d5c  jb      short loc_180060D0B
0x180060d5e  mov     edx, 42h ; 'B'
0x180060d63  mov     r9d, 8004101Dh
0x180060d69  jmp     loc_180060E08
0x180060d6e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060d74  mov     ebx, 80041008h
0x180060d79  mov     edx, ebx
0x180060d7b  mov     rcx, rax
0x180060d7e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060d84  lea     rax, WPP_GLOBAL_Control
0x180060d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180060d92  cmp     rcx, rax
0x180060d95  jz      loc_180060D0B
0x180060d9b  test    byte ptr [rcx+1Ch], 1
0x180060d9f  jz      loc_180060D0B
0x180060da5  cmp     byte ptr [rcx+19h], 2
0x180060da9  jb      loc_180060D0B
0x180060daf  mov     edx, 44h ; 'D'
0x180060db4  mov     r9d, 80041008h
0x180060dba  jmp     short loc_180060E08
0x180060dbc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060dc2  mov     ebx, 80041006h
0x180060dc7  mov     edx, ebx
0x180060dc9  mov     rcx, rax
0x180060dcc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060dd2  lea     rax, WPP_GLOBAL_Control
0x180060dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180060de0  cmp     rcx, rax
0x180060de3  jz      loc_180060D0B
0x180060de9  test    byte ptr [rcx+1Ch], 1
0x180060ded  jz      loc_180060D0B
0x180060df3  cmp     byte ptr [rcx+19h], 2
0x180060df7  jb      loc_180060D0B
0x180060dfd  mov     edx, 45h ; 'E'
0x180060e02  mov     r9d, 80041006h
0x180060e08  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180060e0f  mov     rcx, [rcx+10h]
0x180060e13  call    WPP_SF_d
0x180060e18  jmp     loc_180060D0B
0x180060e1d  cmp     byte ptr [rcx+19h], 2
0x180060e21  jb      loc_180060D0B
0x180060e27  mov     edx, 46h ; 'F'
0x180060e2c  mov     r9d, ebx
0x180060e2f  jmp     short loc_180060E08
0x180060e31  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060e37  mov     ebx, 80041008h
0x180060e3c  mov     edx, ebx
0x180060e3e  mov     rcx, rax
0x180060e41  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060e47  lea     rax, WPP_GLOBAL_Control
0x180060e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e55  cmp     rcx, rax
0x180060e58  jz      loc_180060D0B
0x180060e5e  test    byte ptr [rcx+1Ch], 1
0x180060e62  jz      loc_180060D0B
0x180060e68  cmp     byte ptr [rcx+19h], 2
0x180060e6c  jb      loc_180060D0B
0x180060e72  mov     edx, 40h ; '@'
0x180060e77  jmp     loc_180060DB4
0x180060e7c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060e82  mov     ebx, 80041008h
0x180060e87  mov     edx, ebx
0x180060e89  mov     rcx, rax
0x180060e8c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060e92  lea     rax, WPP_GLOBAL_Control
0x180060e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180060ea0  cmp     rcx, rax
0x180060ea3  jz      loc_180060D0B
0x180060ea9  test    byte ptr [rcx+1Ch], 1
0x180060ead  jz      loc_180060D0B
0x180060eb3  cmp     byte ptr [rcx+19h], 2
0x180060eb7  jb      loc_180060D0B
0x180060ebd  mov     edx, 41h ; 'A'
0x180060ec2  jmp     loc_180060DB4
0x180060ec7  mov     edx, [rdi+1Ch]
0x180060eca  mov     rcx, rbx
0x180060ecd  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180060ed3  cmp     qword ptr [rax], 0
0x180060ed7  jz      loc_180060C89
0x180060edd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180060ee3  mov     ebx, 80041006h
0x180060ee8  mov     edx, ebx
0x180060eea  mov     rcx, rax
0x180060eed  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180060ef3  lea     rax, WPP_GLOBAL_Control
0x180060efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180060f01  cmp     rcx, rax
0x180060f04  jz      loc_180060D0B
0x180060f0a  test    byte ptr [rcx+1Ch], 1
0x180060f0e  jz      loc_180060D0B
0x180060f14  cmp     byte ptr [rcx+19h], 2
0x180060f18  jb      loc_180060D0B
0x180060f1e  mov     edx, 43h ; 'C'
0x180060f23  jmp     loc_180060E02
```
