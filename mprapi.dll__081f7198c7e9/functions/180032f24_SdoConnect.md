# SdoConnect

- ea: `0x180032f24`
- end: `0x18003311b`
- name: `SdoConnect`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a710`

## callees

- `0x180002718`
- `0x180032f24`
- `0x180033fe8`
- `0x180034034`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x1800511f0`
- `0x180053010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033089`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033089`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180032ff5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180032ff5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180033009`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180033009`
- `OLEAUT32!__imp_SysAllocString` at `0x180032fdb`
- `OLEAUT32!__imp_SysAllocString` at `0x180032fdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180033016`
- `OLEAUT32!__imp_SysFreeString` at `0x1800330e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180033016`
- `OLEAUT32!__imp_SysFreeString` at `0x1800330e7`

## string_xrefs

- `0x1800330af`: `SdoConnect: %x on OpenServer(%hs) \n`

## pseudocode

```c
__int64 __fastcall SdoConnect(__int64 a1, const OLECHAR *a2, unsigned int a3, SdoMachine **a4)
{
  const OLECHAR *v7; // rcx
  OLECHAR *v8; // rbx
  int v9; // edi
  __int64 result; // rax
  SdoMachine *v11; // rax
  SdoMachine *v12; // rsi
  DWORD nSize[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[2044]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR Buffer[1024]; // [rsp+830h] [rbp+730h] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( (_QWORD)xmmword_180078D60 )
  {
    LOWORD(v14) = 0;
    FormatRRASErrorString(&v14, L"SdoConnect: entered %hs, %d\n", a2, a3);
    ((void (__fastcall *)(__int64, _QWORD, int *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      xmmword_180078D60,
      &v14);
  }
  if ( !a2 )
    goto LABEL_11;
  nSize[0] = 1024;
  if ( !*a2 )
    goto LABEL_11;
  if ( *a2 == 92 )
    v7 = a2 + 2;
  else
    v7 = a2;
  v8 = SysAllocString(v7);
  if ( !v8 )
    return 8;
  if ( GetComputerNameW(Buffer, nSize) && !lstrcmpiW(Buffer, v8) )
  {
    SysFreeString(v8);
LABEL_11:
    v8 = 0;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    goto LABEL_22;
  }
  *a4 = 0;
  v11 = (SdoMachine *)operator new(0x20u);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    goto LABEL_22;
  }
  *(_QWORD *)v11 = 0;
  *((_DWORD *)v11 + 2) = 0;
  *((_DWORD *)v11 + 3) = a3;
  *((_QWORD *)v11 + 3) = 0;
  *((_DWORD *)v11 + 4) = a3 == 0;
  v9 = SdoMachine::Attach((LPVOID *)v11, v8);
  if ( v9 )
  {
    SdoMachine::~SdoMachine(v12);
    operator delete(v12);
    if ( v9 >= 0 )
      goto LABEL_24;
LABEL_22:
    if ( (_QWORD)xmmword_180078D60 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"SdoConnect: %x on OpenServer(%hs) \n", (unsigned int)v9, v8);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSdoWrapperTemplateFunc)(
        gSdoWrapperEtwContext,
        xmmword_180078D60,
        &v14);
    }
    goto LABEL_24;
  }
  *a4 = v12;
LABEL_24:
  if ( v8 )
    SysFreeString(v8);
  result = 0;
  if ( v9 < 0 )
    return (unsigned int)v9;
  return result;
}

```

## disassembly

```asm
0x180032f24  mov     [rsp-8+arg_0], rbx
0x180032f29  push    rbp
0x180032f2a  push    rsi
0x180032f2b  push    rdi
0x180032f2c  push    r14
0x180032f2e  push    r15
0x180032f30  lea     rbp, [rsp-0F40h]
0x180032f38  mov     eax, 1040h
0x180032f3d  call    _alloca_probe
0x180032f42  sub     rsp, rax
0x180032f45  mov     rax, cs:__security_cookie
0x180032f4c  xor     rax, rsp
0x180032f4f  mov     [rbp+0F60h+var_30], rax
0x180032f56  mov     edi, r8d
0x180032f59  lea     rcx, [rsp+1060h+var_102C]; void *
0x180032f5e  mov     rbx, rdx
0x180032f61  xor     r15d, r15d
0x180032f64  xor     edx, edx; Val
0x180032f66  mov     [rsp+1060h+var_1030], r15d
0x180032f6b  mov     r8d, 7FCh; Size
0x180032f71  mov     r14, r9
0x180032f74  call    memset_0
0x180032f79  cmp     qword ptr cs:xmmword_180078D60, r15
0x180032f80  jz      short loc_180032FBE
0x180032f82  mov     r9d, edi
0x180032f85  mov     word ptr [rsp+1060h+var_1030], r15w
0x180032f8b  mov     r8, rbx
0x180032f8e  lea     rdx, aSdoconnectEnte; "SdoConnect: entered %hs, %d\n"
0x180032f95  lea     rcx, [rsp+1060h+var_1030]
0x180032f9a  call    FormatRRASErrorString
0x180032f9f  mov     rdx, qword ptr cs:xmmword_180078D60
0x180032fa6  lea     r8, [rsp+1060h+var_1030]
0x180032fab  mov     rcx, cs:gSdoWrapperEtwContext
0x180032fb2  mov     rax, cs:gSdoWrapperTemplateFunc
0x180032fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fbe  test    rbx, rbx
0x180032fc1  jz      short loc_18003301C
0x180032fc3  mov     [rsp+1060h+nSize], 400h
0x180032fcb  cmp     [rbx], r15w
0x180032fcf  jz      short loc_18003301C
0x180032fd1  cmp     word ptr [rbx], 5Ch ; '\'
0x180032fd5  jnz     short loc_18003302B
0x180032fd7  lea     rcx, [rbx+4]; psz
0x180032fdb  call    cs:__imp_SysAllocString
0x180032fe1  mov     rbx, rax
0x180032fe4  test    rax, rax
0x180032fe7  jz      short loc_180033030
0x180032fe9  lea     rdx, [rsp+1060h+nSize]; nSize
0x180032fee  lea     rcx, [rbp+0F60h+Buffer]; lpBuffer
0x180032ff5  call    cs:__imp_GetComputerNameW
0x180032ffb  test    eax, eax
0x180032ffd  jz      short loc_18003301F
0x180032fff  mov     rdx, rbx; lpString2
0x180033002  lea     rcx, [rbp+0F60h+Buffer]; lpString1
0x180033009  call    cs:__imp_lstrcmpiW
0x18003300f  test    eax, eax
0x180033011  jnz     short loc_18003301F
0x180033013  mov     rcx, rbx; bstrString
0x180033016  call    cs:__imp_SysFreeString
0x18003301c  mov     rbx, r15
0x18003301f  test    r14, r14
0x180033022  jnz     short loc_18003303A
0x180033024  mov     edi, 80070057h
0x180033029  jmp     short loc_18003309A
0x18003302b  mov     rcx, rbx
0x18003302e  jmp     short loc_180032FDB
0x180033030  mov     eax, 8
0x180033035  jmp     loc_1800330F5
0x18003303a  mov     ecx, 20h ; ' '; Size
0x18003303f  mov     [r14], r15
0x180033042  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033047  mov     rsi, rax
0x18003304a  test    rax, rax
0x18003304d  jz      short loc_180033095
0x18003304f  mov     ecx, r15d
0x180033052  mov     [rax], r15
0x180033055  test    edi, edi
0x180033057  mov     [rax+8], r15d
0x18003305b  mov     rdx, rbx; unsigned __int16 *
0x18003305e  mov     [rax+0Ch], edi
0x180033061  setz    cl
0x180033064  mov     [rax+18h], r15
0x180033068  mov     [rax+10h], ecx
0x18003306b  mov     rcx, rax; this
0x18003306e  call    ?Attach@SdoMachine@@QEAAJPEAG@Z; SdoMachine::Attach(ushort *)
0x180033073  mov     edi, eax
0x180033075  test    eax, eax
0x180033077  jnz     short loc_18003307E
0x180033079  mov     [r14], rsi
0x18003307c  jmp     short loc_1800330DF
0x18003307e  mov     rcx, rsi; this
0x180033081  call    ??1SdoMachine@@QEAA@XZ; SdoMachine::~SdoMachine(void)
0x180033086  mov     rcx, rsi
0x180033089  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003308f  test    edi, edi
0x180033091  jns     short loc_1800330DF
0x180033093  jmp     short loc_18003309A
0x180033095  mov     edi, 8007000Eh
0x18003309a  cmp     qword ptr cs:xmmword_180078D60, r15
0x1800330a1  jz      short loc_1800330DF
0x1800330a3  mov     r9, rbx
0x1800330a6  mov     word ptr [rsp+1060h+var_1030], r15w
0x1800330ac  mov     r8d, edi
0x1800330af  lea     rdx, aSdoconnectXOnO; "SdoConnect: %x on OpenServer(%hs) \n"
0x1800330b6  lea     rcx, [rsp+1060h+var_1030]
0x1800330bb  call    FormatRRASErrorString
0x1800330c0  mov     rdx, qword ptr cs:xmmword_180078D60
0x1800330c7  lea     r8, [rsp+1060h+var_1030]
0x1800330cc  mov     rcx, cs:gSdoWrapperEtwContext
0x1800330d3  mov     rax, cs:gSdoWrapperTemplateFunc
0x1800330da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330df  test    rbx, rbx
0x1800330e2  jz      short loc_1800330ED
0x1800330e4  mov     rcx, rbx; bstrString
0x1800330e7  call    cs:__imp_SysFreeString
0x1800330ed  test    edi, edi
0x1800330ef  mov     eax, r15d
0x1800330f2  cmovs   eax, edi
0x1800330f5  mov     rcx, [rbp+0F60h+var_30]
0x1800330fc  xor     rcx, rsp; StackCookie
0x1800330ff  call    __security_check_cookie
0x180033104  mov     rbx, [rsp+1060h+arg_0]
0x18003310c  add     rsp, 1040h
0x180033113  pop     r15
0x180033115  pop     r14
0x180033117  pop     rdi
0x180033118  pop     rsi
0x180033119  pop     rbp
0x18003311a  retn
```
