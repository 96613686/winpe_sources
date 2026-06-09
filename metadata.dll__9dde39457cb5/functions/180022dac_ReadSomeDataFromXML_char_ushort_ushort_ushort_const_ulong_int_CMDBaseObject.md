# ReadSomeDataFromXML(char *,ushort *,ushort *,ushort const *,ulong,int,CMDBaseObject * *)

- ea: `0x180022dac`
- end: `0x180022ecf`
- name: `?ReadSomeDataFromXML@@YAJPEADPEAG1PEBGKHPEAPEAVCMDBaseObject@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(char *, unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, unsigned int, int, struct CMDBaseObject **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180018ae0`

## callees

- `0x180012e88`
- `0x180012ec0`
- `0x180013344`
- `0x180022dac`

## import_xrefs

- `ole32!CoRevertToSelf` at `0x180022eb4`
- `ole32!CoRevertToSelf` at `0x180022eb4`
- `ole32!CoImpersonateClient` at `0x180022de9`
- `ole32!CoImpersonateClient` at `0x180022de9`
- `KERNEL32!WaitForSingleObject` at `0x180022de3`
- `KERNEL32!WaitForSingleObject` at `0x180022de3`
- `KERNEL32!ReleaseSemaphore` at `0x180022ea9`
- `KERNEL32!ReleaseSemaphore` at `0x180022ea9`
- `IisRTL!PuDbgPrint` at `0x180022e95`
- `IisRTL!PuDbgPrint` at `0x180022e95`

## string_xrefs

- `0x180022e77`: `ReadSomeDataFromXML`

## pseudocode

```c
__int64 __fastcall ReadSomeDataFromXML(
        char *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        struct CMDBaseObject **a7)
{
  HRESULT inited; // eax
  unsigned int v10; // ebx
  char v11; // di
  __int64 v12; // r8
  _BYTE v14[32]; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-48h]
  char *v16; // [rsp+58h] [rbp-40h]
  char v17; // [rsp+60h] [rbp-38h]

  v15 = a2;
  v16 = a1;
  memset(v14, 0, sizeof(v14));
  v17 = 0;
  WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  inited = CoImpersonateClient();
  v10 = inited;
  if ( inited < 0 )
  {
    v11 = 0;
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_11;
    v12 = 12124;
    goto LABEL_10;
  }
  v11 = 1;
  v17 = 1;
  inited = CImporter::InitIST((CImporter *)v14);
  v10 = inited;
  if ( inited < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) == 0 )
      goto LABEL_11;
    v12 = 12132;
    goto LABEL_10;
  }
  inited = CImporter::DoIt((CImporter *)v14, a3, a4, a5, a7);
  v10 = inited;
  if ( inited < 0 && (g_dwDebugFlags & 0xF) != 0 )
  {
    v12 = 12139;
LABEL_10:
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\metadata\\metasub.cxx", v12, "ReadSomeDataFromXML", "hr=0x%x\n", inited);
  }
LABEL_11:
  ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  if ( v11 )
    CoRevertToSelf();
  CImporter::~CImporter((CImporter *)v14);
  return v10;
}

```

## disassembly

```asm
0x180022dac  mov     rax, rsp
0x180022daf  push    rbx
0x180022db0  push    rbp
0x180022db1  push    rsi
0x180022db2  push    rdi
0x180022db3  sub     rsp, 78h
0x180022db7  xorps   xmm0, xmm0
0x180022dba  mov     [rax-48h], rdx
0x180022dbe  xorps   xmm1, xmm1
0x180022dc1  mov     [rax-40h], rcx
0x180022dc5  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180022dcc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022dcf  movdqu  xmmword ptr [rax-68h], xmm0
0x180022dd4  mov     rsi, r9
0x180022dd7  mov     rbp, r8
0x180022dda  movdqu  xmmword ptr [rax-58h], xmm1
0x180022ddf  mov     byte ptr [rax-38h], 0
0x180022de3  call    cs:__imp_WaitForSingleObject
0x180022de9  call    cs:__imp_CoImpersonateClient
0x180022def  mov     ebx, eax
0x180022df1  test    eax, eax
0x180022df3  jns     short loc_180022E0D
0x180022df5  xor     dil, dil
0x180022df8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180022dff  jz      loc_180022E9B
0x180022e05  mov     r8d, 2F5Ch
0x180022e0b  jmp     short loc_180022E70
0x180022e0d  mov     dil, 1
0x180022e10  lea     rcx, [rsp+98h+var_68]; this
0x180022e15  mov     [rsp+98h+var_38], dil
0x180022e1a  call    ?InitIST@CImporter@@AEAAJXZ; CImporter::InitIST(void)
0x180022e1f  mov     ebx, eax
0x180022e21  test    eax, eax
0x180022e23  jns     short loc_180022E36
0x180022e25  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180022e2c  jz      short loc_180022E9B
0x180022e2e  mov     r8d, 2F64h
0x180022e34  jmp     short loc_180022E70
0x180022e36  mov     rax, [rsp+98h+arg_30]
0x180022e3e  lea     rcx, [rsp+98h+var_68]; this
0x180022e43  mov     r9d, [rsp+98h+arg_20]; unsigned int
0x180022e4b  mov     r8, rsi; unsigned __int16 *
0x180022e4e  mov     rdx, rbp; unsigned __int16 *
0x180022e51  mov     [rsp+98h+var_78], rax; struct CMDBaseObject **
0x180022e56  call    ?DoIt@CImporter@@QEAAJPEAGPEBGKPEAPEAVCMDBaseObject@@@Z; CImporter::DoIt(ushort *,ushort const *,ulong,CMDBaseObject * *)
0x180022e5b  mov     ebx, eax
0x180022e5d  test    eax, eax
0x180022e5f  jns     short loc_180022E9B
0x180022e61  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180022e68  jz      short loc_180022E9B
0x180022e6a  mov     r8d, 2F6Bh
0x180022e70  mov     rcx, cs:g_pDebug
0x180022e77  lea     r9, aReadsomedatafr; "ReadSomeDataFromXML"
0x180022e7e  mov     [rsp+98h+var_70], eax
0x180022e82  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180022e89  lea     rax, aHr0xX; "hr=0x%x\n"
0x180022e90  mov     [rsp+98h+var_78], rax
0x180022e95  call    cs:__imp_PuDbgPrint
0x180022e9b  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x180022ea2  xor     r8d, r8d; lpPreviousCount
0x180022ea5  lea     edx, [r8+1]; lReleaseCount
0x180022ea9  call    cs:__imp_ReleaseSemaphore
0x180022eaf  test    dil, dil
0x180022eb2  jz      short loc_180022EBA
0x180022eb4  call    cs:__imp_CoRevertToSelf
0x180022eba  lea     rcx, [rsp+98h+var_68]; this
0x180022ebf  call    ??1CImporter@@QEAA@XZ; CImporter::~CImporter(void)
0x180022ec4  mov     eax, ebx
0x180022ec6  add     rsp, 78h
0x180022eca  pop     rdi
0x180022ecb  pop     rsi
0x180022ecc  pop     rbp
0x180022ecd  pop     rbx
0x180022ece  retn
```
