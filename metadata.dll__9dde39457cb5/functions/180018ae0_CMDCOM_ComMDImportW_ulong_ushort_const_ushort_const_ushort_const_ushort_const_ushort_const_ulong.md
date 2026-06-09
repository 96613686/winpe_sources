# CMDCOM::ComMDImportW(ulong,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180018ae0`
- end: `0x180018d45`
- name: `?ComMDImportW@CMDCOM@@UEAAJKPEBG0000K@Z`
- size: `613`
- prototype: `__int64 __fastcall(CMDCOM *this, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180008a08`
- `0x180008a14`
- `0x180018ae0`
- `0x18001c580`
- `0x180022dac`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180018ba0`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x180018ba0`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180018c08`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180018c08`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180018b73`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180018b73`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180018cf7`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180018d0b`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180018cf7`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180018d0b`
- `IisRTL!PuDbgPrint` at `0x180018ccc`
- `IisRTL!PuDbgPrint` at `0x180018ccc`

## string_xrefs

- `0x180018cc0`: `inetsrv\iis\mb\metadata\comobj.cxx`
- `0x180018c4f`: `[CMDCOM::ComMDImportW] ReadSomeDataFromXML failed - error 0x%08lx\n`
- `0x180018cb9`: `CMDCOM::ComMDImportW`
- `0x180018cab`: `[CMDCOM::ComMDImportW] CopyMetaObject failed - error 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDImportW(
        CMDCOM *this,
        unsigned int a2,
        unsigned __int8 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned int a8)
{
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rdi
  unsigned __int16 *v15; // r14
  __int64 v16; // rcx
  unsigned __int16 v17; // ax
  char *StrA; // rax
  int v19; // eax
  struct CMDBaseObject *v20; // rsi
  unsigned int v21; // edi
  int v22; // eax
  int v23; // [rsp+28h] [rbp-100h]
  unsigned __int8 *v24; // [rsp+28h] [rbp-100h]
  unsigned __int8 *v25; // [rsp+28h] [rbp-100h]
  struct CMDBaseObject *v26; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v27[128]; // [rsp+60h] [rbp-C8h] BYREF

  if ( !a6 || !a7 || !a3 || !a4 )
    return 2147942487LL;
  if ( (a8 & 0xFFFFFFF8) != 0 && a8 )
    return 2147943404LL;
  STRAU::STRAU((STRAU *)v27);
  if ( !g_dwInitialized )
  {
    v12 = -2146646016;
LABEL_30:
    STRAU::~STRAU((STRAU *)v27);
    return v12;
  }
  v13 = (const unsigned __int16 *)&qword_18003A6B0;
  if ( a5 )
    v13 = a5;
  if ( !STRAU::Copy((STRAU *)v27, v13) )
    goto LABEL_29;
  v26 = 0;
  v14 = -1;
  do
    ++v14;
  while ( a7[v14] );
  v15 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)(v14 + 1), 2u));
  if ( !v15 )
  {
LABEL_29:
    v12 = -2147024882;
    goto LABEL_30;
  }
  v16 = 0;
  do
  {
    v17 = a7[v16];
    if ( v17 == 92 )
      v17 = 47;
    v15[v16] = v17;
    v16 = (unsigned int)(v16 + 1);
  }
  while ( (unsigned int)v16 <= (unsigned int)v14 );
  StrA = STRAU::QueryStrA((STRAU *)v27);
  v19 = ReadSomeDataFromXML(StrA, a6, v15, a4, a8, v23, &v26);
  v20 = v26;
  v21 = v19;
  if ( v19 >= 0 )
  {
    v22 = CopyMetaObject(0, (unsigned __int8 *)&qword_18003A6B0, 0, v26, a2, a3, (a8 & 4) == 0, 1, 1);
    v21 = v22;
    if ( v22 < 0 && (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v25) = v22;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
        4822,
        "CMDCOM::ComMDImportW",
        "[CMDCOM::ComMDImportW] CopyMetaObject failed - error 0x%08lx\n",
        v25);
    }
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v24) = v19;
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\comobj.cxx",
      4801,
      "CMDCOM::ComMDImportW",
      "[CMDCOM::ComMDImportW] ReadSomeDataFromXML failed - error 0x%08lx\n",
      v24);
  }
  if ( v20 )
    (**(void (__fastcall ***)(struct CMDBaseObject *, __int64))v20)(v20, 1);
  operator delete(v15);
  STRAU::~STRAU((STRAU *)v27);
  return v21;
}

```

## disassembly

```asm
0x180018ae0  mov     [rsp+arg_0], rbx
0x180018ae5  push    rbp
0x180018ae6  push    rsi
0x180018ae7  push    rdi
0x180018ae8  push    r12
0x180018aea  push    r13
0x180018aec  push    r14
0x180018aee  push    r15
0x180018af0  sub     rsp, 0F0h
0x180018af7  mov     rax, cs:__security_cookie
0x180018afe  xor     rax, rsp
0x180018b01  mov     [rsp+128h+var_48], rax
0x180018b09  mov     r12, [rsp+128h+arg_28]
0x180018b11  xor     r14d, r14d
0x180018b14  mov     rdi, [rsp+128h+arg_20]
0x180018b1c  mov     rbp, r9
0x180018b1f  mov     rsi, [rsp+128h+arg_30]
0x180018b27  mov     r15, r8
0x180018b2a  mov     r13d, edx
0x180018b2d  test    r12, r12
0x180018b30  jz      loc_180018D15
0x180018b36  test    rsi, rsi
0x180018b39  jz      loc_180018D15
0x180018b3f  test    r8, r8
0x180018b42  jz      loc_180018D15
0x180018b48  test    r9, r9
0x180018b4b  jz      loc_180018D15
0x180018b51  mov     ebx, [rsp+128h+arg_38]
0x180018b58  test    ebx, 0FFFFFFF8h
0x180018b5e  jz      short loc_180018B6E
0x180018b60  test    ebx, ebx
0x180018b62  jz      short loc_180018B6E
0x180018b64  mov     eax, 800703ECh
0x180018b69  jmp     loc_180018D1A
0x180018b6e  lea     rcx, [rsp+128h+var_C8]
0x180018b73  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180018b79  mov     eax, cs:?g_dwInitialized@@3KC; ulong volatile g_dwInitialized
0x180018b7f  test    eax, eax
0x180018b81  jnz     short loc_180018B8D
0x180018b83  mov     ebx, 800CC800h
0x180018b88  jmp     loc_180018D06
0x180018b8d  test    rdi, rdi
0x180018b90  lea     rdx, qword_18003A6B0
0x180018b97  lea     rcx, [rsp+128h+var_C8]
0x180018b9c  cmovnz  rdx, rdi
0x180018ba0  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x180018ba6  test    eax, eax
0x180018ba8  jz      loc_180018D01
0x180018bae  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018bb2  mov     [rsp+128h+var_D8], r14
0x180018bb7  mov     rdi, r8
0x180018bba  inc     rdi
0x180018bbd  cmp     [rsi+rdi*2], r14w
0x180018bc2  jnz     short loc_180018BBA
0x180018bc4  lea     ecx, [rdi+1]
0x180018bc7  mov     eax, 2
0x180018bcc  mul     rcx
0x180018bcf  cmovb   rax, r8
0x180018bd3  mov     rcx, rax; unsigned __int64
0x180018bd6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018bdb  mov     r14, rax
0x180018bde  test    rax, rax
0x180018be1  jz      loc_180018D01
0x180018be7  xor     ecx, ecx
0x180018be9  movzx   eax, word ptr [rsi+rcx*2]
0x180018bed  cmp     ax, 5Ch ; '\'
0x180018bf1  jnz     short loc_180018BF8
0x180018bf3  mov     eax, 2Fh ; '/'
0x180018bf8  mov     [r14+rcx*2], ax
0x180018bfd  inc     ecx
0x180018bff  cmp     ecx, edi
0x180018c01  jbe     short loc_180018BE9
0x180018c03  lea     rcx, [rsp+128h+var_C8]
0x180018c08  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180018c0e  mov     r9, rbp; unsigned __int16 *
0x180018c11  mov     r8, r14; unsigned __int16 *
0x180018c14  mov     rcx, rax; char *
0x180018c17  mov     rdx, r12; unsigned __int16 *
0x180018c1a  lea     rax, [rsp+128h+var_D8]
0x180018c1f  mov     [rsp+128h+var_F8], rax; struct CMDBaseObject **
0x180018c24  mov     [rsp+128h+var_108], ebx; unsigned int
0x180018c28  call    ?ReadSomeDataFromXML@@YAJPEADPEAG1PEBGKHPEAPEAVCMDBaseObject@@@Z; ReadSomeDataFromXML(char *,ushort *,ushort *,ushort const *,ulong,int,CMDBaseObject * *)
0x180018c2d  mov     rsi, [rsp+128h+var_D8]
0x180018c32  mov     edi, eax
0x180018c34  test    eax, eax
0x180018c36  jns     short loc_180018C58
0x180018c38  test    byte ptr cs:g_dwDebugFlags, 3
0x180018c3f  jz      loc_180018CD2
0x180018c45  mov     dword ptr [rsp+128h+var_100], eax
0x180018c49  mov     r8d, 12C1h
0x180018c4f  lea     rax, aCmdcomCommdimp_0; "[CMDCOM::ComMDImportW] ReadSomeDataFrom"...
0x180018c56  jmp     short loc_180018CB2
0x180018c58  mov     [rsp+128h+var_E8], 1; int
0x180018c60  lea     rdx, qword_18003A6B0; unsigned __int8 *
0x180018c67  mov     [rsp+128h+var_F0], 1; int
0x180018c6f  mov     r9, rsi; struct CMDBaseObject *
0x180018c72  shr     ebx, 2
0x180018c75  xor     r8d, r8d; int
0x180018c78  not     ebx
0x180018c7a  xor     ecx, ecx; unsigned int
0x180018c7c  and     ebx, 1
0x180018c7f  mov     dword ptr [rsp+128h+var_F8], ebx; int
0x180018c83  mov     [rsp+128h+var_100], r15; unsigned __int8 *
0x180018c88  mov     [rsp+128h+var_108], r13d; unsigned int
0x180018c8d  call    ?CopyMetaObject@@YAJKPEAEHPEAVCMDBaseObject@@K0HHH@Z; CopyMetaObject(ulong,uchar *,int,CMDBaseObject *,ulong,uchar *,int,int,int)
0x180018c92  mov     edi, eax
0x180018c94  test    eax, eax
0x180018c96  jns     short loc_180018CD2
0x180018c98  test    byte ptr cs:g_dwDebugFlags, 3
0x180018c9f  jz      short loc_180018CD2
0x180018ca1  mov     dword ptr [rsp+128h+var_100], eax
0x180018ca5  mov     r8d, 12D6h
0x180018cab  lea     rax, aCmdcomCommdimp_1; "[CMDCOM::ComMDImportW] CopyMetaObject f"...
0x180018cb2  mov     rcx, cs:g_pDebug
0x180018cb9  lea     r9, aCmdcomCommdimp; "CMDCOM::ComMDImportW"
0x180018cc0  lea     rdx, aInetsrvIisMbMe_2; "inetsrv\\iis\\mb\\metadata\\comobj.cxx"
0x180018cc7  mov     qword ptr [rsp+128h+var_108], rax
0x180018ccc  call    cs:__imp_PuDbgPrint
0x180018cd2  test    rsi, rsi
0x180018cd5  jz      short loc_180018CEA
0x180018cd7  mov     rax, [rsi]
0x180018cda  mov     edx, 1
0x180018cdf  mov     rcx, rsi
0x180018ce2  mov     rax, [rax]
0x180018ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cea  mov     rcx, r14; Block
0x180018ced  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018cf2  lea     rcx, [rsp+128h+var_C8]
0x180018cf7  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180018cfd  mov     eax, edi
0x180018cff  jmp     short loc_180018D1A
0x180018d01  mov     ebx, 8007000Eh
0x180018d06  lea     rcx, [rsp+128h+var_C8]
0x180018d0b  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180018d11  mov     eax, ebx
0x180018d13  jmp     short loc_180018D1A
0x180018d15  mov     eax, 80070057h
0x180018d1a  mov     rcx, [rsp+128h+var_48]
0x180018d22  xor     rcx, rsp; StackCookie
0x180018d25  call    __security_check_cookie
0x180018d2a  mov     rbx, [rsp+128h+arg_0]
0x180018d32  add     rsp, 0F0h
0x180018d39  pop     r15
0x180018d3b  pop     r14
0x180018d3d  pop     r13
0x180018d3f  pop     r12
0x180018d41  pop     rdi
0x180018d42  pop     rsi
0x180018d43  pop     rbp
0x180018d44  retn
```
