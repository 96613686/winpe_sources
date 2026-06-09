# CMSDAInitialize::GetInitializationString(IUnknown *,uchar,ushort * *)

- ea: `0x18001fef0`
- end: `0x18002017a`
- name: `?GetInitializationString@CMSDAInitialize@@UEAAJPEAUIUnknown@@EPEAPEAG@Z`
- size: `650`
- prototype: `int(CMSDAInitialize *__hidden this, struct IUnknown *, unsigned __int8, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180013870`
- `0x18001fef0`
- `0x180023aec`
- `0x180029560`
- `0x180029c30`
- `0x18002ec26`
- `0x18003c270`
- `0x180061814`
- `0x180069d9c`
- `0x180087010`

## import_xrefs

- `MSDART!mpFree` at `0x18002007c`
- `MSDART!mpFree` at `0x18002007c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ff62`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001ff62`
- `ole32!CoTaskMemAlloc` at `0x18001ffeb`
- `ole32!CoTaskMemAlloc` at `0x18001ffeb`

## pseudocode

```c
__int64 __fastcall CMSDAInitialize::GetInitializationString(
        CMSDAInitialize *this,
        struct IUnknown *a2,
        unsigned __int8 a3,
        unsigned __int16 **a4)
{
  int v4; // edi
  unsigned int BidID; // eax
  unsigned int v8; // r14d
  int InitializationString; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  int v17; // eax
  _BYTE *v18; // rcx
  __int64 v19; // rax
  int v21; // [rsp+20h] [rbp-20h]
  int v22; // [rsp+28h] [rbp-18h]
  _QWORD v23[2]; // [rsp+30h] [rbp-10h] BYREF
  void *Src; // [rsp+88h] [rbp+48h] BYREF

  v4 = a3;
  v23[0] = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C95E0[0] )
  {
    BidID = CMSDAInitialize::GetBidID(this);
    v22 = (int)a4;
    v21 = v4;
    bidScopeEnterW(v23, off_1800C95E0[0], BidID, a2);
  }
  Src = 0;
  v8 = 0;
  SetErrorInfo(0, 0);
  if ( a4 && a2 )
  {
    *a4 = 0;
    InitializationString = GetInitializationString(a2, v4, (unsigned __int16 **)&Src);
    v10 = InitializationString;
    if ( InitializationString >= 0 )
    {
      if ( !Src )
        goto LABEL_23;
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)Src + v14) );
      v8 = 2 * v14 + 2;
      v15 = (unsigned __int16 *)CoTaskMemAlloc(v8);
      v16 = v15;
      if ( v15 )
      {
        memcpy_0(v15, Src, v8);
        v16[((unsigned __int64)v8 >> 1) - 1] = 0;
        *a4 = v16;
      }
      else
      {
        v17 = PostHResult(0x8007000E, &IID_IDataInitialize);
        v10 = v17;
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v17, L"<CMSDAInitialize::GetInitializationString|OLEDB|ERR> ", 0x117u);
      }
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(InitializationString, L"<CMSDAInitialize::GetInitializationString|OLEDB|ERR> ", 0x10Bu);
      PostHResult(v10, &IID_IDataInitialize);
    }
  }
  else
  {
    v10 = PostHResult(0x80070057, &IID_IDataInitialize);
  }
  v18 = Src;
  if ( Src )
  {
    v19 = v8;
    if ( v8 )
    {
      do
      {
        *v18++ = 0;
        --v19;
      }
      while ( v19 );
      v18 = Src;
    }
    mpFree(v18, v11, v12, v13);
  }
LABEL_23:
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(v10, L"<CMSDAInitialize::GetInitializationString|OLEDB|ERR> ", 0x126u);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (v10 & 0x80000000) != 0 )
      {
        if ( off_1800C93A0[0] )
          bidTraceW(off_1800C8468[0], 303104, off_1800C93A0[0], v10, (_DWORD)a4, v22, v23[0]);
      }
      else if ( off_1800C93A8[0] )
      {
        bidTraceW(off_1800C8468[0], 303104, off_1800C93A8[0], v10, v21, v22, v23[0]);
      }
      if ( (bidGblFlags & 4) != 0 && v23[0] != -1 && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD *))off_1800BC0E8[0])(bidID, 0, 0, v23);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C8468[0],
                               304137,
                               L"<CMSDAInitialize::GetInitializationString|Trace|HR> ",
                               v10);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18001fef0  mov     [rsp-28h+arg_0], rbx
0x18001fef5  mov     [rsp-28h+arg_8], rsi
0x18001fefa  push    rbp
0x18001fefb  push    rdi
0x18001fefc  push    r12
0x18001fefe  push    r14
0x18001ff00  push    r15
0x18001ff02  mov     rbp, rsp
0x18001ff05  sub     rsp, 40h
0x18001ff09  xor     r12d, r12d
0x18001ff0c  movzx   edi, r8b
0x18001ff10  test    byte ptr cs:_bidGblFlags, 4
0x18001ff17  mov     r15, r9
0x18001ff1a  mov     rbx, rdx
0x18001ff1d  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x18001ff25  jz      short loc_18001FF57
0x18001ff27  mov     rax, cs:off_1800C95E0; "<IDataInitialize::GetInitializationStri"...
0x18001ff2e  test    rax, rax
0x18001ff31  jz      short loc_18001FF57
0x18001ff33  call    ?GetBidID@CMSDAInitialize@@QEAAHXZ; CMSDAInitialize::GetBidID(void)
0x18001ff38  mov     rdx, cs:off_1800C95E0; "<IDataInitialize::GetInitializationStri"...
0x18001ff3f  lea     rcx, [rbp+var_10]
0x18001ff43  mov     r9, rbx
0x18001ff46  mov     [rsp+40h+var_18], r15
0x18001ff4b  mov     r8d, eax
0x18001ff4e  mov     dword ptr [rsp+40h+var_20], edi
0x18001ff52  call    _bidScopeEnterW
0x18001ff57  xor     edx, edx; perrinfo
0x18001ff59  mov     [rbp+Src], r12
0x18001ff5d  xor     ecx, ecx; dwReserved
0x18001ff5f  mov     r14d, r12d
0x18001ff62  call    cs:__imp_SetErrorInfo
0x18001ff68  test    r15, r15
0x18001ff6b  jz      loc_180020048
0x18001ff71  test    rbx, rbx
0x18001ff74  jz      loc_180020048
0x18001ff7a  lea     r8, [rbp+Src]; unsigned __int16 **
0x18001ff7e  mov     [r15], r12
0x18001ff81  mov     dl, dil; unsigned __int8
0x18001ff84  mov     rcx, rbx; struct IUnknown *
0x18001ff87  call    ?GetInitializationString@@YAJPEAUIUnknown@@EPEAPEAG@Z; GetInitializationString(IUnknown *,uchar,ushort * *)
0x18001ff8c  mov     ebx, eax
0x18001ff8e  test    eax, eax
0x18001ff90  jns     short loc_18001FFC2
0x18001ff92  test    byte ptr cs:_bidGblFlags, 2
0x18001ff99  jz      short loc_18001FFAF
0x18001ff9b  mov     r8d, 10Bh; unsigned int
0x18001ffa1  lea     rdx, aCmsdainitializ_9; "<CMSDAInitialize::GetInitializationStri"...
0x18001ffa8  mov     ecx, eax; int
0x18001ffaa  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001ffaf  lea     rdx, IID_IDataInitialize; struct _GUID *
0x18001ffb6  mov     ecx, ebx; int
0x18001ffb8  call    ?PostHResult@@YAJJPEBU_GUID@@@Z; PostHResult(long,_GUID const *)
0x18001ffbd  jmp     loc_18002005B
0x18001ffc2  mov     rcx, [rbp+Src]
0x18001ffc6  test    rcx, rcx
0x18001ffc9  jz      loc_180020082
0x18001ffcf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ffd3  inc     rax
0x18001ffd6  cmp     [rcx+rax*2], r12w
0x18001ffdb  jnz     short loc_18001FFD3
0x18001ffdd  lea     r14d, ds:2[rax*2]
0x18001ffe5  mov     ecx, r14d; cb
0x18001ffe8  mov     edi, r14d
0x18001ffeb  call    cs:__imp_CoTaskMemAlloc
0x18001fff1  mov     rsi, rax
0x18001fff4  test    rax, rax
0x18001fff7  jnz     short loc_18002002B
0x18001fff9  lea     rdx, IID_IDataInitialize; struct _GUID *
0x180020000  mov     ecx, 8007000Eh; int
0x180020005  call    ?PostHResult@@YAJJPEBU_GUID@@@Z; PostHResult(long,_GUID const *)
0x18002000a  test    byte ptr cs:_bidGblFlags, 2
0x180020011  mov     ebx, eax
0x180020013  jz      short loc_18002005B
0x180020015  mov     r8d, 117h; unsigned int
0x18002001b  lea     rdx, aCmsdainitializ_9; "<CMSDAInitialize::GetInitializationStri"...
0x180020022  mov     ecx, eax; int
0x180020024  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180020029  jmp     short loc_18002005B
0x18002002b  mov     rdx, [rbp+Src]; Src
0x18002002f  mov     r8, rdi; Size
0x180020032  mov     rcx, rsi; void *
0x180020035  call    memcpy_0
0x18002003a  shr     rdi, 1
0x18002003d  mov     [rsi+rdi*2-2], r12w
0x180020043  mov     [r15], rsi
0x180020046  jmp     short loc_18002005B
0x180020048  lea     rdx, IID_IDataInitialize; struct _GUID *
0x18002004f  mov     ecx, 80070057h; int
0x180020054  call    ?PostHResult@@YAJJPEBU_GUID@@@Z; PostHResult(long,_GUID const *)
0x180020059  mov     ebx, eax
0x18002005b  mov     rcx, [rbp+Src]
0x18002005f  test    rcx, rcx
0x180020062  jz      short loc_180020082
0x180020064  mov     eax, r14d
0x180020067  test    r14d, r14d
0x18002006a  jz      short loc_18002007C
0x18002006c  mov     [rcx], r12b
0x18002006f  inc     rcx
0x180020072  sub     rax, 1
0x180020076  jnz     short loc_18002006C
0x180020078  mov     rcx, [rbp+Src]
0x18002007c  call    cs:__imp_mpFree
0x180020082  test    byte ptr cs:_bidGblFlags, 2
0x180020089  jz      loc_180020161
0x18002008f  mov     r8d, 126h; unsigned int
0x180020095  lea     rdx, aCmsdainitializ_9; "<CMSDAInitialize::GetInitializationStri"...
0x18002009c  mov     ecx, ebx; int
0x18002009e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800200a3  test    byte ptr cs:_bidGblFlags, 2
0x1800200aa  jz      loc_180020161
0x1800200b0  test    ebx, ebx
0x1800200b2  js      short loc_1800200DD
0x1800200b4  mov     rax, cs:off_1800C93A8; "<IDataInitialize::GetInitializationStri"...
0x1800200bb  test    rax, rax
0x1800200be  jz      short loc_180020109
0x1800200c0  mov     r8, cs:off_1800C93A8; "<IDataInitialize::GetInitializationStri"...
0x1800200c7  mov     r9d, ebx
0x1800200ca  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800200d1  mov     edx, 4A000h
0x1800200d6  call    _bidTraceW
0x1800200db  jmp     short loc_180020109
0x1800200dd  mov     rax, cs:off_1800C93A0; "<IDataInitialize::GetInitializationStri"...
0x1800200e4  test    rax, rax
0x1800200e7  jz      short loc_180020109
0x1800200e9  mov     r8, cs:off_1800C93A0; "<IDataInitialize::GetInitializationStri"...
0x1800200f0  mov     r9d, ebx
0x1800200f3  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800200fa  mov     edx, 4A000h
0x1800200ff  mov     [rsp+40h+var_20], r15
0x180020104  call    _bidTraceW
0x180020109  test    byte ptr cs:_bidGblFlags, 4
0x180020110  jz      short loc_18002013B
0x180020112  cmp     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180020117  jz      short loc_18002013B
0x180020119  mov     rcx, cs:_bidID
0x180020120  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020124  jz      short loc_18002013B
0x180020126  mov     rax, cs:off_1800BC0E8
0x18002012d  lea     r9, [rbp+var_10]
0x180020131  xor     r8d, r8d
0x180020134  xor     edx, edx
0x180020136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002013b  test    byte ptr cs:_bidGblFlags, 2
0x180020142  jz      short loc_180020161
0x180020144  mov     rcx, cs:off_1800C8468; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18002014b  lea     r8, aCmsdainitializ_7; "<CMSDAInitialize::GetInitializationStri"...
0x180020152  mov     r9d, ebx
0x180020155  mov     edx, 4A409h
0x18002015a  call    _bidTraceHR
0x18002015f  mov     ebx, eax
0x180020161  mov     rsi, [rsp+40h+arg_8]
0x180020166  mov     eax, ebx
0x180020168  mov     rbx, [rsp+40h+arg_0]
0x18002016d  add     rsp, 40h
0x180020171  pop     r15
0x180020173  pop     r14
0x180020175  pop     r12
0x180020177  pop     rdi
0x180020178  pop     rbp
0x180020179  retn
```
