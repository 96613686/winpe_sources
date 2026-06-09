# ViewerFactory::reportError(long,IXMLDOMParseError *)

- ea: `0x1800e7e68`
- end: `0x1800e8255`
- name: `?reportError@ViewerFactory@@QEAAJJPEAUIXMLDOMParseError@@@Z`
- size: `1005`
- prototype: `__int64 __fastcall(ViewerFactory *__hidden this, int, struct IXMLDOMParseError *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e11c8`
- `0x1800e5e00`
- `0x1800e6310`

## callees

- `0x1800222c0`
- `0x18002ac90`
- `0x18002d7e0`
- `0x180046640`
- `0x180059078`
- `0x180064034`
- `0x180064d24`
- `0x1800e5648`
- `0x1800e5f78`
- `0x1800e74c0`
- `0x1800e7d04`
- `0x1800e7e68`
- `0x1800e8434`
- `0x180102d20`
- `0x180102db0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800e8173`
- `msvcrt!_resetstkoflw` at `0x1800e8173`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e81c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e81c6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e8161`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800e8161`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8210`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8219`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8224`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8210`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8219`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e8224`

## pseudocode

```c
__int64 __fastcall ViewerFactory::reportError(ViewerFactory *this, int a2, struct IXMLDOMParseError *a3)
{
  unsigned __int16 *v5; // rbx
  int v6; // esi
  struct IXMLDOMParseError *v8; // rcx
  __int64 v9; // rcx
  BSTR v10; // r9
  int v11; // r8d
  unsigned __int16 v12; // cx
  unsigned __int16 v13; // dx
  struct String *v14; // rax
  struct String *v15; // rax
  struct String *v16; // rbx
  struct String *v17; // rax
  struct String *v18; // rax
  int v19; // [rsp+40h] [rbp-10E8h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-10E0h] BYREF
  int v21; // [rsp+50h] [rbp-10D8h] BYREF
  struct IXMLDOMParseError *v22; // [rsp+58h] [rbp-10D0h] BYREF
  int v23; // [rsp+60h] [rbp-10C8h]
  BSTR v24; // [rsp+68h] [rbp-10C0h] BYREF
  unsigned __int16 *v25; // [rsp+70h] [rbp-10B8h]
  _BYTE v26[8]; // [rsp+78h] [rbp-10B0h] BYREF
  BSTR i; // [rsp+80h] [rbp-10A8h]
  ViewerFactory *v28; // [rsp+88h] [rbp-10A0h]
  unsigned __int16 v29[2096]; // [rsp+90h] [rbp-1098h] BYREF

  v28 = this;
  v22 = a3;
  bstrString = 0;
  v24 = 0;
  v5 = 0;
  v25 = 0;
  v21 = 0;
  v19 = 0;
  v6 = ModelInit::init(v26, 0, a3);
  if ( v6 >= 0 )
  {
    v8 = v22;
    if ( v22 || (ViewerFactory::getParseError(this, &v22), (v8 = v22) != 0) )
    {
      ((void (__fastcall *)(struct IXMLDOMParseError *, BSTR *))v8->lpVtbl->get_reason)(v8, &bstrString);
      if ( !*((_BYTE *)this + 144) )
      {
        ((void (__fastcall *)(struct IXMLDOMParseError *, BSTR *))v22->lpVtbl->get_url)(v22, &v24);
        ((void (__fastcall *)(struct IXMLDOMParseError *, int *))v22->lpVtbl->get_line)(v22, &v19);
        ((void (__fastcall *)(struct IXMLDOMParseError *, int *))v22->lpVtbl->get_linepos)(v22, &v21);
        v9 = *((_QWORD *)this + 15);
        if ( v9 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v9 + 48LL))(v9) )
          (*(void (__fastcall **)(_QWORD, BSTR, _QWORD, _QWORD, BSTR, char))(**((_QWORD **)this + 15) + 40LL))(
            *((_QWORD *)this + 15),
            v24,
            (unsigned int)v19,
            (unsigned int)v21,
            bstrString,
            1);
        v10 = v24;
        if ( v24 && *v24 )
        {
          v11 = 0;
          v23 = 0;
          for ( i = v24; ; i = v10 )
          {
            v12 = *v10;
            if ( !*v10 || v11 >= 2091 )
              break;
            if ( v12 == 60 || v12 == 62 )
            {
              v29[v11] = 38;
              v13 = 108;
              if ( v12 != 60 )
                v13 = 103;
              v29[v11 + 1] = v13;
              v29[v11 + 2] = 116;
              v29[v11 + 3] = 59;
              v11 += 4;
            }
            else
            {
              v29[v11++] = v12;
            }
            v23 = v11;
            ++v10;
          }
          if ( (unsigned __int64)(2LL * v11) >= 0x1060 )
            _report_rangecheckfailure();
          v29[v11] = 0;
          v14 = String::newString(v29);
          v15 = Resources::formatMessage(-1072896638, v14, 0, 0, 0);
          bstrString = AppendBSTR(bstrString, v15);
        }
        if ( v19 > 0 )
        {
          v16 = String::valueOf(v21, 10);
          v17 = String::valueOf(v19, 10);
          v18 = Resources::formatMessage(-1072897023, v17, v16, 0, 0);
          bstrString = AppendBSTR(bstrString, v18);
        }
        v5 = FormatSourceInfo(v22);
        v25 = v5;
      }
      ViewerFactory::writeError(this, bstrString, v5);
    }
    else
    {
      ViewerFactory::reportError2(this, a2);
    }
    SysFreeString(bstrString);
    SysFreeString(v5);
    SysFreeString(v24);
    ModelInit::~ModelInit((ModelInit *)v26);
    return 0;
  }
  else
  {
    ModelInit::~ModelInit((ModelInit *)v26);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1800e7e68  push    rbx
0x1800e7e6a  push    rsi
0x1800e7e6b  push    rdi
0x1800e7e6c  push    r14
0x1800e7e6e  push    r15
0x1800e7e70  mov     eax, 1100h
0x1800e7e75  call    _alloca_probe
0x1800e7e7a  sub     rsp, rax
0x1800e7e7d  mov     rax, cs:__security_cookie
0x1800e7e84  xor     rax, rsp
0x1800e7e87  mov     [rsp+1128h+var_38], rax
0x1800e7e8f  mov     r14d, edx
0x1800e7e92  mov     rdi, rcx
0x1800e7e95  mov     [rsp+1128h+var_10A0], rcx
0x1800e7e9d  mov     [rsp+1128h+var_10D0], r8
0x1800e7ea2  xor     r15d, r15d
0x1800e7ea5  mov     [rsp+1128h+bstrString], r15
0x1800e7eaa  mov     [rsp+1128h+var_10C0], r15
0x1800e7eaf  mov     ebx, r15d
0x1800e7eb2  mov     [rsp+1128h+var_10B8], rbx
0x1800e7eb7  mov     [rsp+1128h+var_10D8], r15d
0x1800e7ebc  mov     [rsp+1128h+var_10E8], r15d
0x1800e7ec1  xor     edx, edx
0x1800e7ec3  lea     rcx, [rsp+1128h+var_10B0]
0x1800e7ec8  call    ?init@ModelInit@@QEAAJW4RentalEnum@@@Z; ModelInit::init(RentalEnum)
0x1800e7ecd  mov     esi, eax
0x1800e7ecf  test    eax, eax
0x1800e7ed1  jns     short loc_1800E7EE4
0x1800e7ed3  lea     rcx, [rsp+1128h+var_10B0]; this
0x1800e7ed8  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800e7edd  mov     eax, esi
0x1800e7edf  jmp     loc_1800E8236
0x1800e7ee4  mov     rcx, [rsp+1128h+var_10D0]
0x1800e7ee9  test    rcx, rcx
0x1800e7eec  jnz     short loc_1800E7F09
0x1800e7eee  lea     rdx, [rsp+1128h+var_10D0]; struct IXMLDOMParseError **
0x1800e7ef3  mov     rcx, rdi; this
0x1800e7ef6  call    ?getParseError@ViewerFactory@@QEAAJPEAPEAUIXMLDOMParseError@@@Z; ViewerFactory::getParseError(IXMLDOMParseError * *)
0x1800e7efb  mov     rcx, [rsp+1128h+var_10D0]
0x1800e7f00  test    rcx, rcx
0x1800e7f03  jz      loc_1800E814B
0x1800e7f09  mov     rax, [rcx]
0x1800e7f0c  lea     rdx, [rsp+1128h+bstrString]
0x1800e7f11  mov     rax, [rax+48h]
0x1800e7f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7f1a  cmp     [rdi+90h], r15b
0x1800e7f21  jnz     loc_1800E8141
0x1800e7f27  mov     rcx, [rsp+1128h+var_10D0]
0x1800e7f2c  mov     rax, [rcx]
0x1800e7f2f  lea     rdx, [rsp+1128h+var_10C0]
0x1800e7f34  mov     rax, [rax+40h]
0x1800e7f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7f3d  mov     rcx, [rsp+1128h+var_10D0]
0x1800e7f42  mov     rax, [rcx]
0x1800e7f45  lea     rdx, [rsp+1128h+var_10E8]
0x1800e7f4a  mov     rax, [rax+58h]
0x1800e7f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7f53  mov     rcx, [rsp+1128h+var_10D0]
0x1800e7f58  mov     rax, [rcx]
0x1800e7f5b  lea     rdx, [rsp+1128h+var_10D8]
0x1800e7f60  mov     rax, [rax+60h]
0x1800e7f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7f69  mov     rcx, [rdi+78h]
0x1800e7f6d  test    rcx, rcx
0x1800e7f70  jz      short loc_1800E7FB3
0x1800e7f72  mov     rax, [rcx]
0x1800e7f75  mov     rax, [rax+30h]
0x1800e7f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7f7e  test    al, al
0x1800e7f80  jnz     short loc_1800E7FB3
0x1800e7f82  mov     rcx, [rdi+78h]
0x1800e7f86  mov     rax, [rcx]
0x1800e7f89  mov     r10, [rax+28h]
0x1800e7f8d  mov     [rsp+1128h+var_1100], 1
0x1800e7f92  mov     rax, [rsp+1128h+bstrString]
0x1800e7f97  mov     [rsp+1128h+var_1108], rax
0x1800e7f9c  mov     r9d, [rsp+1128h+var_10D8]
0x1800e7fa1  mov     r8d, [rsp+1128h+var_10E8]
0x1800e7fa6  mov     rdx, [rsp+1128h+var_10C0]
0x1800e7fab  mov     rax, r10
0x1800e7fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7fb3  mov     r9, [rsp+1128h+var_10C0]
0x1800e7fb8  test    r9, r9
0x1800e7fbb  jz      loc_1800E80E0
0x1800e7fc1  cmp     [r9], r15w
0x1800e7fc5  jz      loc_1800E80E0
0x1800e7fcb  mov     r8d, r15d
0x1800e7fce  mov     [rsp+1128h+var_10C8], r15d
0x1800e7fd3  mov     [rsp+1128h+var_10A8], r9
0x1800e7fdb  mov     r10d, 3Ch ; '<'
0x1800e7fe1  movzx   ecx, word ptr [r9]
0x1800e7fe5  cmp     r15w, cx
0x1800e7fe9  jz      loc_1800E8089
0x1800e7fef  cmp     r8d, 82Bh
0x1800e7ff6  jge     loc_1800E8089
0x1800e7ffc  cmp     cx, r10w
0x1800e8000  jz      short loc_1800E8018
0x1800e8002  cmp     cx, 3Eh ; '>'
0x1800e8006  jz      short loc_1800E8018
0x1800e8008  movsxd  rax, r8d
0x1800e800b  mov     [rsp+rax*2+1128h+var_1098], cx
0x1800e8013  inc     r8d
0x1800e8016  jmp     short loc_1800E8073
0x1800e8018  movsxd  rax, r8d
0x1800e801b  mov     edx, 26h ; '&'
0x1800e8020  mov     [rsp+rax*2+1128h+var_1098], dx
0x1800e8028  mov     edx, 6Ch ; 'l'
0x1800e802d  lea     eax, [rdx-5]
0x1800e8030  cmp     r10w, cx
0x1800e8034  cmovnz  dx, ax
0x1800e8038  lea     eax, [r8+1]
0x1800e803c  movsxd  rcx, eax
0x1800e803f  mov     [rsp+rcx*2+1128h+var_1098], dx
0x1800e8047  lea     eax, [r8+2]
0x1800e804b  movsxd  rcx, eax
0x1800e804e  mov     eax, 74h ; 't'
0x1800e8053  mov     [rsp+rcx*2+1128h+var_1098], ax
0x1800e805b  lea     eax, [r8+3]
0x1800e805f  movsxd  rcx, eax
0x1800e8062  mov     eax, 3Bh ; ';'
0x1800e8067  mov     [rsp+rcx*2+1128h+var_1098], ax
0x1800e806f  add     r8d, 4
0x1800e8073  mov     [rsp+1128h+var_10C8], r8d
0x1800e8078  add     r9, 2
0x1800e807c  mov     [rsp+1128h+var_10A8], r9
0x1800e8084  jmp     loc_1800E7FE1
0x1800e8089  movsxd  rax, r8d
0x1800e808c  lea     rcx, [rax+rax]
0x1800e8090  cmp     rcx, 1060h
0x1800e8097  jnb     short loc_1800E80DB
0x1800e8099  mov     [rsp+rcx+1128h+var_1098], r15w
0x1800e80a2  lea     rcx, [rsp+1128h+var_1098]; unsigned __int16 *
0x1800e80aa  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800e80af  mov     [rsp+1128h+var_1108], r15; struct String *
0x1800e80b4  xor     r9d, r9d; struct String *
0x1800e80b7  xor     r8d, r8d; struct String *
0x1800e80ba  mov     rdx, rax; struct String *
0x1800e80bd  mov     ecx, 0C00CE582h; int
0x1800e80c2  call    ?formatMessage@Resources@@SAPEAVString@@JPEAV2@000@Z; Resources::formatMessage(long,String *,String *,String *,String *)
0x1800e80c7  mov     rdx, rax; struct String *
0x1800e80ca  mov     rcx, [rsp+1128h+bstrString]; bstrString
0x1800e80cf  call    ?AppendBSTR@@YAPEAGPEAGPEAVString@@@Z; AppendBSTR(ushort *,String *)
0x1800e80d4  mov     [rsp+1128h+bstrString], rax
0x1800e80d9  jmp     short loc_1800E80E0
0x1800e80db  call    __report_rangecheckfailure
0x1800e80e0  cmp     [rsp+1128h+var_10E8], r15d
0x1800e80e5  jle     short loc_1800E812F
0x1800e80e7  mov     esi, 0Ah
0x1800e80ec  mov     edx, esi; int
0x1800e80ee  mov     ecx, [rsp+1128h+var_10D8]; int
0x1800e80f2  call    ?valueOf@String@@SAPEAV1@HH@Z; String::valueOf(int,int)
0x1800e80f7  mov     rbx, rax
0x1800e80fa  mov     edx, esi; int
0x1800e80fc  mov     ecx, [rsp+1128h+var_10E8]; int
0x1800e8100  call    ?valueOf@String@@SAPEAV1@HH@Z; String::valueOf(int,int)
0x1800e8105  mov     [rsp+1128h+var_1108], r15; struct String *
0x1800e810a  xor     r9d, r9d; struct String *
0x1800e810d  mov     r8, rbx; struct String *
0x1800e8110  mov     rdx, rax; struct String *
0x1800e8113  mov     ecx, 0C00CE401h; int
0x1800e8118  call    ?formatMessage@Resources@@SAPEAVString@@JPEAV2@000@Z; Resources::formatMessage(long,String *,String *,String *,String *)
0x1800e811d  mov     rdx, rax; struct String *
0x1800e8120  mov     rcx, [rsp+1128h+bstrString]; bstrString
0x1800e8125  call    ?AppendBSTR@@YAPEAGPEAGPEAVString@@@Z; AppendBSTR(ushort *,String *)
0x1800e812a  mov     [rsp+1128h+bstrString], rax
0x1800e812f  mov     rcx, [rsp+1128h+var_10D0]; struct IXMLDOMParseError *
0x1800e8134  call    ?FormatSourceInfo@@YAPEAGPEAUIXMLDOMParseError@@@Z; FormatSourceInfo(IXMLDOMParseError *)
0x1800e8139  mov     rbx, rax
0x1800e813c  mov     [rsp+1128h+var_10B8], rax
0x1800e8141  mov     rdx, [rsp+1128h+bstrString]
0x1800e8146  jmp     loc_1800E8200
0x1800e814b  mov     edx, r14d; int
0x1800e814e  mov     rcx, rdi; this
0x1800e8151  call    ?reportError2@ViewerFactory@@QEAAJJ@Z; ViewerFactory::reportError2(long)
0x1800e8156  jmp     loc_1800E820B
0x1800e815b  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800e8161  call    cs:__imp_TlsGetValue
0x1800e8167  mov     rbx, rax
0x1800e816a  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800e8171  jnz     short loc_1800E81EC
0x1800e8173  call    cs:__imp__resetstkoflw
0x1800e8179  test    eax, eax
0x1800e817b  jnz     short loc_1800E81CE
0x1800e817d  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800e8184  test    rcx, rcx
0x1800e8187  jz      short loc_1800E819B
0x1800e8189  cmp     [rcx+50h], rbx
0x1800e818d  jnz     short loc_1800E819B
0x1800e818f  mov     rax, [rcx]
0x1800e8192  mov     rax, [rax+20h]
0x1800e8196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e819b  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800e81a2  test    rcx, rcx
0x1800e81a5  jz      short loc_1800E81B9
0x1800e81a7  cmp     [rcx+50h], rbx
0x1800e81ab  jnz     short loc_1800E81B9
0x1800e81ad  mov     rax, [rcx]
0x1800e81b0  mov     rax, [rax+20h]
0x1800e81b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e81b9  xor     r9d, r9d; lpArguments
0x1800e81bc  xor     r8d, r8d; nNumberOfArguments
0x1800e81bf  xor     edx, edx; dwExceptionFlags
0x1800e81c1  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800e81c6  call    cs:__imp_RaiseException
0x1800e81cc  jmp     short loc_1800E81EC
0x1800e81ce  mov     rax, [rbx+60h]
0x1800e81d2  mov     [rbx+68h], rax
0x1800e81d6  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x1800e81dd  mov     [rbx+60h], rax
0x1800e81e1  mov     dword ptr [rbx+54h], 800703E9h
0x1800e81e8  mov     byte ptr [rbx+78h], 0
0x1800e81ec  xor     edx, edx; unsigned __int16 *
0x1800e81ee  mov     [rsp+1128h+bstrString], rdx
0x1800e81f3  mov     rbx, [rsp+1128h+var_10B8]
0x1800e81f8  mov     rdi, [rsp+1128h+var_10A0]
0x1800e8200  mov     r8, rbx; unsigned __int16 *
0x1800e8203  mov     rcx, rdi; this
0x1800e8206  call    ?writeError@ViewerFactory@@QEAAJPEAG0@Z; ViewerFactory::writeError(ushort *,ushort *)
0x1800e820b  mov     rcx, [rsp+1128h+bstrString]; bstrString
0x1800e8210  call    cs:__imp_SysFreeString
0x1800e8216  mov     rcx, rbx; bstrString
0x1800e8219  call    cs:__imp_SysFreeString
0x1800e821f  mov     rcx, [rsp+1128h+var_10C0]; bstrString
0x1800e8224  call    cs:__imp_SysFreeString
0x1800e822a  lea     rcx, [rsp+1128h+var_10B0]; this
0x1800e822f  call    ??1ModelInit@@QEAA@XZ; ModelInit::~ModelInit(void)
0x1800e8234  xor     eax, eax
0x1800e8236  mov     rcx, [rsp+1128h+var_38]
0x1800e823e  xor     rcx, rsp; StackCookie
0x1800e8241  call    __security_check_cookie
0x1800e8246  add     rsp, 1100h
0x1800e824d  pop     r15
0x1800e824f  pop     r14
0x1800e8251  pop     rdi
0x1800e8252  pop     rsi
0x1800e8253  pop     rbx
0x1800e8254  retn
0x180103d50  push    rbp
0x180103d52  sub     rsp, 40h
0x180103d56  mov     rbp, rdx
0x180103d59  xor     edx, edx; bool
0x180103d5b  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103d60  nop
0x180103d61  add     rsp, 40h
0x180103d65  pop     rbp
0x180103d66  retn
```
