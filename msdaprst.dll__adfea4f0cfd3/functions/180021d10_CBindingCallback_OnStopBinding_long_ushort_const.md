# CBindingCallback::OnStopBinding(long,ushort const *)

- ea: `0x180021d10`
- end: `0x180022230`
- name: `?OnStopBinding@CBindingCallback@@UEAAJJPEBG@Z`
- size: `1312`
- prototype: `__int64 __fastcall(CBindingCallback *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x180002770`
- `0x1800028b8`
- `0x18001b008`
- `0x180021d10`
- `0x18002dca4`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180021ffe`
- `KERNEL32!MultiByteToWideChar` at `0x180021ffe`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180022169`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180022169`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180022055`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180022055`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CBindingCallback::OnStopBinding(CBindingCallback *this, unsigned int a2, const unsigned __int16 *a3)
{
  _QWORD *v3; // r15
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  unsigned int v9; // edx
  int v10; // ebx
  unsigned __int8 *v11; // rbx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  CHAR *v16; // r13
  unsigned __int8 *v17; // rdi
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  CHAR *lpWideCharStr; // r12
  unsigned __int128 v24; // rax
  int v25; // eax
  int v26; // r14d
  int v27; // eax
  int v28; // r14d
  HRESULT v29; // eax
  int v30; // r14d
  int v31; // eax
  int v32; // r14d
  int v33; // eax
  int v34; // r14d
  HRESULT v35; // eax
  int v36; // r14d
  CHAR MultiByteStr[4]; // [rsp+40h] [rbp+0h] BYREF
  int v39; // [rsp+44h] [rbp+4h] BYREF
  __int64 v40; // [rsp+48h] [rbp+8h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+50h] [rbp+10h] BYREF
  IErrorInfo *perrinfo; // [rsp+58h] [rbp+18h] BYREF
  unsigned __int8 *v43; // [rsp+60h] [rbp+20h]
  unsigned __int8 *v44; // [rsp+68h] [rbp+28h]
  char *v45; // [rsp+70h] [rbp+30h]
  __int64 v46; // [rsp+78h] [rbp+38h] BYREF

  try
  {
    v40 = 0;
    pperrinfo = 0;
    perrinfo = 0;
    v39 = 0;
    *(_DWORD *)MultiByteStr = 0;
    v3 = (_QWORD *)((char *)this + 24);
    v45 = (char *)this + 24;
    v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
           *((_QWORD *)this + 3),
           &IID_IWinInetHttpInfo,
           &v40);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049BE8[0] )
          bidTraceW(off_1800491F8[0], 441344, off_180049BE8[0], (unsigned int)v4, 431);
      }
      ThrowHR(v5);
    }
    *(_DWORD *)MultiByteStr = 4;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, int *, CHAR *, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
           v40,
           536870931,
           &v39,
           MultiByteStr,
           0,
           0);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049BE0[0] )
        bidTraceW(off_1800491F8[0], 445440, off_180049BE0[0], (unsigned int)v6, 435);
      ThrowHR(v7);
    }
    if ( v39 == 500 )
    {
      *(_DWORD *)MultiByteStr = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, CHAR *, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
             v40,
             20,
             0,
             MultiByteStr,
             0,
             0);
      v10 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049BD8[0] )
          bidTraceW(off_1800491F8[0], 456704, off_180049BD8[0], (unsigned int)v8, 446);
        ThrowHR(v10);
      }
      if ( *(_DWORD *)MultiByteStr > 1u )
      {
        v11 = 0;
        v43 = 0;
        if ( *(_DWORD *)MultiByteStr > 0x400u )
        {
          v11 = MMMAlloc(*(unsigned int *)MultiByteStr, v9);
          v43 = v11;
          v16 = (CHAR *)v11;
        }
        else
        {
          v12 = *(unsigned int *)MultiByteStr + 15LL;
          if ( v12 <= *(unsigned int *)MultiByteStr )
            v12 = 0xFFFFFFFFFFFFFF0LL;
          v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
          v14 = alloca(v13);
          v15 = alloca(v13);
          v16 = MultiByteStr;
        }
        OnNullThrowOOM(v16);
        v17 = 0;
        v44 = 0;
        if ( *(_DWORD *)MultiByteStr > 0x200u )
        {
          v24 = *(unsigned int *)MultiByteStr * (unsigned __int128)2uLL;
          if ( !is_mul_ok(*(unsigned int *)MultiByteStr, 2u) )
            LODWORD(v24) = -1;
          v17 = MMMAlloc(v24, DWORD2(v24));
          v44 = v17;
          lpWideCharStr = (CHAR *)v17;
        }
        else
        {
          v18 = 2LL * *(unsigned int *)MultiByteStr;
          v19 = v18 + 15;
          if ( v18 + 15 < v18 )
            v19 = 0xFFFFFFFFFFFFFF0LL;
          v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
          v21 = alloca(v20);
          v22 = alloca(v20);
          lpWideCharStr = MultiByteStr;
        }
        OnNullThrowOOM(lpWideCharStr);
        v16[*(_DWORD *)MultiByteStr - 1] = 0;
        v25 = (*(__int64 (__fastcall **)(__int64, __int64, CHAR *, CHAR *, _QWORD, _QWORD))(*(_QWORD *)v40 + 32LL))(
                v40,
                20,
                v16,
                MultiByteStr,
                0,
                0);
        v26 = v25;
        if ( v25 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049BD0[0] )
            bidTraceW(off_1800491F8[0], 466944, off_180049BD0[0], (unsigned int)v25, 456);
          ThrowHR(v26);
        }
        v27 = MultiByteToWideChar(
                0,
                0,
                v16,
                *(_DWORD *)MultiByteStr + 1,
                (LPWSTR)lpWideCharStr,
                *(_DWORD *)MultiByteStr + 1);
        v28 = v27;
        if ( v27 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049BC8[0] )
            bidTraceW(off_1800491F8[0], 471040, off_180049BC8[0], (unsigned int)v27, 460);
          ThrowHR(v28);
        }
        v29 = CreateErrorInfo(&pperrinfo);
        v30 = v29;
        if ( v29 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049BC0[0] )
            bidTraceW(off_1800491F8[0], 479232, off_180049BC0[0], (unsigned int)v29, 468);
          ThrowHR(v30);
        }
        v31 = ((__int64 (__fastcall *)(ICreateErrorInfo *, CHAR *))pperrinfo->lpVtbl->SetDescription)(
                pperrinfo,
                lpWideCharStr);
        v32 = v31;
        if ( v31 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049BB8[0] )
            bidTraceW(off_1800491F8[0], 480256, off_180049BB8[0], (unsigned int)v31, 469);
          ThrowHR(v32);
        }
        v33 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                pperrinfo,
                &IID_IErrorInfo,
                &perrinfo);
        v34 = v33;
        if ( v33 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049BB0[0] )
            bidTraceW(off_1800491F8[0], 481280, off_180049BB0[0], (unsigned int)v33, 470);
          ThrowHR(v34);
        }
        v35 = SetErrorInfo(0, perrinfo);
        v36 = v35;
        if ( v35 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049BA8[0] )
            bidTraceW(off_1800491F8[0], 482304, off_180049BA8[0], (unsigned int)v35, 471);
          ThrowHR(v36);
        }
        operator delete(v17);
        operator delete(v11);
      }
    }
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v40);
  }
  catch ( long v46 )
  {
    v3 = v45;
  }
  if ( *v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
    *v3 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180021d10  mov     [rsp-8+arg_8], edx
0x180021d14  push    rbp
0x180021d15  push    rbx
0x180021d16  push    rsi
0x180021d17  push    rdi
0x180021d18  push    r12
0x180021d1a  push    r13
0x180021d1c  push    r14
0x180021d1e  push    r15
0x180021d20  sub     rsp, 98h
0x180021d27  lea     rbp, [rsp+40h]
0x180021d2c  mov     rax, cs:__security_cookie
0x180021d33  xor     rax, rbp
0x180021d36  mov     [rbp+90h+var_50], rax
0x180021d3a  xor     esi, esi
0x180021d3c  mov     [rbp+90h+var_88], rsi
0x180021d40  mov     [rbp+90h+pperrinfo], rsi
0x180021d44  mov     [rbp+90h+perrinfo], rsi
0x180021d48  mov     [rbp+90h+var_8C], esi
0x180021d4b  mov     dword ptr [rbp+90h+MultiByteStr], esi
0x180021d4e  lea     r15, [rcx+18h]
0x180021d52  mov     [rbp+90h+var_60], r15
0x180021d56  mov     rcx, [r15]
0x180021d59  mov     rax, [rcx]
0x180021d5c  lea     r8, [rbp+90h+var_88]
0x180021d60  lea     rdx, IID_IWinInetHttpInfo
0x180021d67  mov     rax, [rax]
0x180021d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d6f  mov     ebx, eax
0x180021d71  test    eax, eax
0x180021d73  jns     short loc_180021DB4
0x180021d75  test    byte ptr cs:_bidGblFlags, 2
0x180021d7c  jz      short loc_180021DAD
0x180021d7e  mov     rcx, cs:off_180049BE8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021d85  test    rcx, rcx
0x180021d88  jz      short loc_180021DAD
0x180021d8a  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1AFh
0x180021d92  mov     r9d, eax
0x180021d95  mov     r8, cs:off_180049BE8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021d9c  mov     edx, 6BC00h
0x180021da1  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021da8  call    _bidTraceW
0x180021dad  mov     ecx, ebx; int
0x180021daf  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021db4  mov     dword ptr [rbp+90h+MultiByteStr], 4
0x180021dbb  mov     rcx, [rbp+90h+var_88]
0x180021dbf  mov     rax, [rcx]
0x180021dc2  mov     qword ptr [rsp+0D0h+cchWideChar], rsi
0x180021dc7  mov     [rsp+0D0h+lpWideCharStr], rsi
0x180021dcc  lea     r9, [rbp+90h+MultiByteStr]
0x180021dd0  lea     r8, [rbp+90h+var_8C]
0x180021dd4  mov     edx, 20000013h
0x180021dd9  mov     rax, [rax+20h]
0x180021ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021de2  mov     ebx, eax
0x180021de4  test    eax, eax
0x180021de6  jns     short loc_180021E27
0x180021de8  test    byte ptr cs:_bidGblFlags, 2
0x180021def  jz      short loc_180021E20
0x180021df1  mov     rcx, cs:off_180049BE0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021df8  test    rcx, rcx
0x180021dfb  jz      short loc_180021E20
0x180021dfd  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1B3h
0x180021e05  mov     r9d, eax
0x180021e08  mov     r8, cs:off_180049BE0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021e0f  mov     edx, 6CC00h
0x180021e14  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021e1b  call    _bidTraceW
0x180021e20  mov     ecx, ebx; int
0x180021e22  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021e27  cmp     [rbp+90h+var_8C], 1F4h
0x180021e2e  jnz     loc_1800221CF
0x180021e34  mov     dword ptr [rbp+90h+MultiByteStr], esi
0x180021e37  mov     rcx, [rbp+90h+var_88]
0x180021e3b  mov     rax, [rcx]
0x180021e3e  mov     qword ptr [rsp+0D0h+cchWideChar], rsi
0x180021e43  mov     [rsp+0D0h+lpWideCharStr], rsi
0x180021e48  lea     r9, [rbp+90h+MultiByteStr]
0x180021e4c  xor     r8d, r8d
0x180021e4f  lea     edx, [r8+14h]
0x180021e53  mov     rax, [rax+20h]
0x180021e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e5c  mov     ebx, eax
0x180021e5e  test    eax, eax
0x180021e60  jns     short loc_180021EA1
0x180021e62  test    byte ptr cs:_bidGblFlags, 2
0x180021e69  jz      short loc_180021E9A
0x180021e6b  mov     rcx, cs:off_180049BD8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021e72  test    rcx, rcx
0x180021e75  jz      short loc_180021E9A
0x180021e77  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1BEh
0x180021e7f  mov     r9d, eax
0x180021e82  mov     r8, cs:off_180049BD8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021e89  mov     edx, 6F800h
0x180021e8e  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021e95  call    _bidTraceW
0x180021e9a  mov     ecx, ebx; int
0x180021e9c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021ea1  mov     ecx, dword ptr [rbp+90h+MultiByteStr]; unsigned int
0x180021ea4  cmp     ecx, 1
0x180021ea7  jbe     loc_1800221CF
0x180021ead  mov     rbx, rsi
0x180021eb0  mov     [rbp+90h+var_70], rbx
0x180021eb4  cmp     ecx, 400h
0x180021eba  ja      short loc_180021EEA
0x180021ebc  mov     eax, ecx
0x180021ebe  add     rcx, 0Fh
0x180021ec2  mov     r14, 0FFFFFFFFFFFFFF0h
0x180021ecc  cmp     rcx, rax
0x180021ecf  ja      short loc_180021ED4
0x180021ed1  mov     rcx, r14
0x180021ed4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180021ed8  mov     rax, rcx
0x180021edb  call    _alloca_probe
0x180021ee0  sub     rsp, rcx
0x180021ee3  lea     r13, [rsp+0D0h+MultiByteStr]
0x180021ee8  jmp     short loc_180021F03
0x180021eea  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180021eef  mov     rbx, rax
0x180021ef2  mov     [rbp+90h+var_70], rax
0x180021ef6  mov     r13, rax
0x180021ef9  mov     r14, 0FFFFFFFFFFFFFF0h
0x180021f03  mov     rcx, r13; void *
0x180021f06  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180021f0b  mov     rdi, rsi
0x180021f0e  mov     [rbp+90h+var_68], rsi
0x180021f12  mov     eax, dword ptr [rbp+90h+MultiByteStr]
0x180021f15  cmp     eax, 200h
0x180021f1a  ja      short loc_180021F41
0x180021f1c  add     rax, rax
0x180021f1f  lea     rcx, [rax+0Fh]
0x180021f23  cmp     rcx, rax
0x180021f26  ja      short loc_180021F2B
0x180021f28  mov     rcx, r14
0x180021f2b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180021f2f  mov     rax, rcx
0x180021f32  call    _alloca_probe
0x180021f37  sub     rsp, rcx
0x180021f3a  lea     r12, [rsp+0D0h+MultiByteStr]
0x180021f3f  jmp     short loc_180021F68
0x180021f41  mov     rcx, rax
0x180021f44  mov     eax, 2
0x180021f49  mul     rcx
0x180021f4c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180021f53  cmovb   rax, rcx
0x180021f57  mov     ecx, eax; unsigned int
0x180021f59  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180021f5e  mov     rdi, rax
0x180021f61  mov     [rbp+90h+var_68], rax
0x180021f65  mov     r12, rax
0x180021f68  mov     rcx, r12; void *
0x180021f6b  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180021f70  mov     eax, dword ptr [rbp+90h+MultiByteStr]
0x180021f73  dec     eax
0x180021f75  mov     [rax+r13], sil
0x180021f79  mov     rcx, [rbp+90h+var_88]
0x180021f7d  mov     rax, [rcx]
0x180021f80  mov     qword ptr [rsp+0D0h+cchWideChar], rsi
0x180021f85  mov     [rsp+0D0h+lpWideCharStr], rsi
0x180021f8a  lea     r9, [rbp+90h+MultiByteStr]
0x180021f8e  mov     r8, r13
0x180021f91  mov     edx, 14h
0x180021f96  mov     rax, [rax+20h]
0x180021f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f9f  mov     r14d, eax
0x180021fa2  test    eax, eax
0x180021fa4  jns     short loc_180021FE6
0x180021fa6  test    byte ptr cs:_bidGblFlags, 2
0x180021fad  jz      short loc_180021FDE
0x180021faf  mov     rcx, cs:off_180049BD0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021fb6  test    rcx, rcx
0x180021fb9  jz      short loc_180021FDE
0x180021fbb  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1C8h
0x180021fc3  mov     r9d, eax
0x180021fc6  mov     r8, cs:off_180049BD0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180021fcd  mov     edx, 72000h
0x180021fd2  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180021fd9  call    _bidTraceW
0x180021fde  mov     ecx, r14d; int
0x180021fe1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180021fe6  mov     r9d, dword ptr [rbp+90h+MultiByteStr]
0x180021fea  inc     r9d; cbMultiByte
0x180021fed  mov     [rsp+0D0h+cchWideChar], r9d; cchWideChar
0x180021ff2  mov     [rsp+0D0h+lpWideCharStr], r12; lpWideCharStr
0x180021ff7  mov     r8, r13; lpMultiByteStr
0x180021ffa  xor     edx, edx; dwFlags
0x180021ffc  xor     ecx, ecx; CodePage
0x180021ffe  call    cs:__imp_MultiByteToWideChar
0x180022005  nop     dword ptr [rax+rax+00h]
0x18002200a  mov     r14d, eax
0x18002200d  test    eax, eax
0x18002200f  jns     short loc_180022051
0x180022011  test    byte ptr cs:_bidGblFlags, 2
0x180022018  jz      short loc_180022049
0x18002201a  mov     rcx, cs:off_180049BC8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180022021  test    rcx, rcx
0x180022024  jz      short loc_180022049
0x180022026  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1CCh
0x18002202e  mov     r9d, eax
0x180022031  mov     r8, cs:off_180049BC8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180022038  mov     edx, 73000h
0x18002203d  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022044  call    _bidTraceW
0x180022049  mov     ecx, r14d; int
0x18002204c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022051  lea     rcx, [rbp+90h+pperrinfo]; pperrinfo
0x180022055  call    cs:__imp_CreateErrorInfo
0x18002205c  nop     dword ptr [rax+rax+00h]
0x180022061  mov     r14d, eax
0x180022064  test    eax, eax
0x180022066  jns     short loc_1800220A8
0x180022068  test    byte ptr cs:_bidGblFlags, 2
0x18002206f  jz      short loc_1800220A0
0x180022071  mov     rcx, cs:off_180049BC0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180022078  test    rcx, rcx
0x18002207b  jz      short loc_1800220A0
0x18002207d  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1D4h
0x180022085  mov     r9d, eax
0x180022088  mov     r8, cs:off_180049BC0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002208f  mov     edx, 75000h
0x180022094  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002209b  call    _bidTraceW
0x1800220a0  mov     ecx, r14d; int
0x1800220a3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800220a8  mov     rcx, [rbp+90h+pperrinfo]
0x1800220ac  mov     rax, [rcx]
0x1800220af  mov     rdx, r12
0x1800220b2  mov     rax, [rax+28h]
0x1800220b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220bb  mov     r14d, eax
0x1800220be  test    eax, eax
0x1800220c0  jns     short loc_180022102
0x1800220c2  test    byte ptr cs:_bidGblFlags, 2
0x1800220c9  jz      short loc_1800220FA
0x1800220cb  mov     rcx, cs:off_180049BB8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800220d2  test    rcx, rcx
0x1800220d5  jz      short loc_1800220FA
0x1800220d7  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1D5h
0x1800220df  mov     r9d, eax
0x1800220e2  mov     r8, cs:off_180049BB8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800220e9  mov     edx, 75400h
0x1800220ee  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800220f5  call    _bidTraceW
0x1800220fa  mov     ecx, r14d; int
0x1800220fd  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022102  mov     rcx, [rbp+90h+pperrinfo]
0x180022106  mov     rax, [rcx]
0x180022109  lea     r8, [rbp+90h+perrinfo]
0x18002210d  lea     rdx, IID_IErrorInfo
0x180022114  mov     rax, [rax]
0x180022117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002211c  mov     r14d, eax
0x18002211f  test    eax, eax
0x180022121  jns     short loc_180022163
0x180022123  test    byte ptr cs:_bidGblFlags, 2
0x18002212a  jz      short loc_18002215B
0x18002212c  mov     rcx, cs:off_180049BB0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x180022133  test    rcx, rcx
0x180022136  jz      short loc_18002215B
0x180022138  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1D6h
0x180022140  mov     r9d, eax
0x180022143  mov     r8, cs:off_180049BB0; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002214a  mov     edx, 75800h
0x18002214f  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022156  call    _bidTraceW
0x18002215b  mov     ecx, r14d; int
0x18002215e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022163  mov     rdx, [rbp+90h+perrinfo]; perrinfo
0x180022167  xor     ecx, ecx; dwReserved
0x180022169  call    cs:__imp_SetErrorInfo
0x180022170  nop     dword ptr [rax+rax+00h]
0x180022175  mov     r14d, eax
0x180022178  test    eax, eax
0x18002217a  jns     short loc_1800221BD
0x18002217c  test    byte ptr cs:_bidGblFlags, 2
0x180022183  jz      short loc_1800221B4
0x180022185  mov     rcx, cs:off_180049BA8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x18002218c  test    rcx, rcx
0x18002218f  jz      short loc_1800221B4
0x180022191  mov     dword ptr [rsp+0D0h+lpWideCharStr], 1D7h
0x180022199  mov     r9d, eax
0x18002219c  mov     r8, cs:off_180049BA8; "<CBindingCallback::OnStopBinding|ADO|ER"...
0x1800221a3  mov     edx, 75C00h
0x1800221a8  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800221af  call    _bidTraceW
0x1800221b4  mov     ecx, r14d; int
0x1800221b7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800221bd  mov     rcx, rdi; void *
0x1800221c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800221c5  nop
0x1800221c6  mov     rcx, rbx; void *
0x1800221c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800221ce  nop
0x1800221cf  lea     rcx, [rbp+90h+perrinfo]
0x1800221d3  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800221d8  nop
0x1800221d9  lea     rcx, [rbp+90h+pperrinfo]
0x1800221dd  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800221e2  nop
0x1800221e3  lea     rcx, [rbp+90h+var_88]
  ... truncated ...
```
