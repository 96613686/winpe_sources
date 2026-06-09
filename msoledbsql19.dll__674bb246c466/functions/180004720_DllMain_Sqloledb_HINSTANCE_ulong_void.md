# DllMain_Sqloledb(HINSTANCE__ *,ulong,void *)

- ea: `0x180004720`
- end: `0x18000490f`
- name: `?DllMain_Sqloledb@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `495`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004920`

## callees

- `0x180003030`
- `0x180003824`
- `0x180003d80`
- `0x180004720`
- `0x180007890`
- `0x180007940`
- `0x180007cf0`
- `0x1801ad6a0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180004799`
- `ADVAPI32!RegOpenKeyExW` at `0x180004799`
- `ADVAPI32!RegQueryValueExW` at `0x1800047cf`
- `ADVAPI32!RegQueryValueExW` at `0x1800047cf`
- `ADVAPI32!RegCloseKey` at `0x1800047e9`
- `ADVAPI32!RegCloseKey` at `0x1800047e9`

## string_xrefs

- `0x18000478b`: `SOFTWARE\Microsoft\MSSQLServer\Client\SQLXMLX`
- `0x1800047c8`: `FORXML_GenerateGUIDBraces`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DllMain_Sqloledb(HINSTANCE a1, int a2, void *a3)
{
  unsigned int v3; // esi
  CError *v4; // rax
  CError *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  CError *v10; // rbx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Ch] BYREF

  v3 = 1;
  if ( !a2 )
  {
    v10 = g_pCError;
    if ( g_pCError )
    {
      CError::~CError(g_pCError);
      operator delete(v10, 0x40u);
      g_pCError = 0;
    }
    if ( g_pMultiLanguage )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD, void *))(*(_QWORD *)g_pMultiLanguage + 16LL))(
        g_pMultiLanguage,
        *(_QWORD *)g_pMultiLanguage,
        a3);
      g_pMultiLanguage = 0;
    }
    return v3;
  }
  if ( a2 != 1 )
    return v3;
  if ( !g_pIMalloc )
    return 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\SQLXMLX", 0, 9u, &hKey)
    && hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    if ( !RegQueryValueExW(hKey, L"FORXML_GenerateGUIDBraces", 0, 0, Data, &cbData) )
      g_fGenerateGUIDSWithBraces = *(_DWORD *)Data != 0;
    RegCloseKey(hKey);
  }
  v4 = (CError *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 88LL))(g_pMO, 64);
  hKey = (HKEY)v4;
  if ( v4 )
    v5 = CError::CError(v4);
  else
    v5 = 0;
  g_pCError = v5;
  if ( v5 )
  {
    v8 = CError::FInit(v5);
    if ( v8 >= 0 )
      return v3;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_20;
    _mm_lfence();
    v7 = (unsigned int)v8;
    v6 = 91145;
LABEL_19:
    bidTraceHR(off_1802601B8[0], v6, v7);
LABEL_20:
    v5 = g_pCError;
    goto LABEL_21;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    v6 = 88073;
    v7 = 2147942414LL;
    goto LABEL_19;
  }
LABEL_21:
  if ( v5 )
  {
    CError::~CError(v5);
    operator delete(v5, 0x40u);
    g_pCError = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180004720  mov     [rsp+arg_0], rbx
0x180004725  push    rsi
0x180004726  sub     rsp, 50h
0x18000472a  mov     rax, cs:__security_cookie
0x180004731  xor     rax, rsp
0x180004734  mov     [rsp+58h+var_18], rax
0x180004739  mov     esi, 1
0x18000473e  test    edx, edx
0x180004740  jz      loc_1800048A5
0x180004746  cmp     edx, esi
0x180004748  jnz     loc_1800048F5
0x18000474e  cmp     cs:?g_pIMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pIMalloc
0x180004756  jnz     short loc_18000475F
0x180004758  xor     esi, esi
0x18000475a  jmp     loc_1800048F5
0x18000475f  mov     [rsp+58h+hKey], 0FFFFFFFFFFFFFFFFh
0x180004768  mov     dword ptr [rsp+58h+Data], 0
0x180004770  mov     [rsp+58h+cbData], 4
0x180004778  lea     rax, [rsp+58h+hKey]
0x18000477d  mov     [rsp+58h+phkResult], rax; phkResult
0x180004782  mov     r9d, 9; samDesired
0x180004788  xor     r8d, r8d; ulOptions
0x18000478b  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x180004792  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004799  call    cs:__imp_RegOpenKeyExW
0x18000479f  test    eax, eax
0x1800047a1  jnz     short loc_1800047F0
0x1800047a3  mov     rcx, [rsp+58h+hKey]; hKey
0x1800047a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800047ac  jz      short loc_1800047F0
0x1800047ae  lea     rax, [rsp+58h+cbData]
0x1800047b3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800047b8  lea     rax, [rsp+58h+Data]
0x1800047bd  mov     [rsp+58h+phkResult], rax; lpData
0x1800047c2  xor     r9d, r9d; lpType
0x1800047c5  xor     r8d, r8d; lpReserved
0x1800047c8  lea     rdx, aForxmlGenerate; "FORXML_GenerateGUIDBraces"
0x1800047cf  call    cs:__imp_RegQueryValueExW
0x1800047d5  test    eax, eax
0x1800047d7  jnz     short loc_1800047E4
0x1800047d9  cmp     dword ptr [rsp+58h+Data], eax
0x1800047dd  setnz   cs:?g_fGenerateGUIDSWithBraces@@3_NA; bool g_fGenerateGUIDSWithBraces
0x1800047e4  mov     rcx, [rsp+58h+hKey]; hKey
0x1800047e9  call    cs:__imp_RegCloseKey
0x1800047ef  nop
0x1800047f0  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800047f7  mov     rax, [rcx]
0x1800047fa  mov     edx, 40h ; '@'
0x1800047ff  mov     rax, [rax+58h]
0x180004803  call    cs:__guard_dispatch_icall_fptr
0x180004809  nop
0x18000480a  mov     [rsp+58h+hKey], rax
0x18000480f  test    rax, rax
0x180004812  jz      short loc_180004821
0x180004814  mov     rcx, rax; this
0x180004817  call    ??0CError@@QEAA@XZ; CError::CError(void)
0x18000481c  mov     rbx, rax
0x18000481f  jmp     short loc_180004823
0x180004821  xor     ebx, ebx
0x180004823  mov     cs:?g_pCError@@3PEAVCError@@EA, rbx; CError * g_pCError
0x18000482a  test    rbx, rbx
0x18000482d  jnz     short loc_180004845
0x18000482f  test    byte ptr cs:_bidGblFlags, 2
0x180004836  jz      short loc_18000487C
0x180004838  mov     edx, 15809h
0x18000483d  mov     r8d, 8007000Eh
0x180004843  jmp     short loc_180004869
0x180004845  mov     rcx, rbx; this
0x180004848  call    ?FInit@CError@@QEAAJXZ; CError::FInit(void)
0x18000484d  test    eax, eax
0x18000484f  jns     loc_1800048F5
0x180004855  test    byte ptr cs:_bidGblFlags, 2
0x18000485c  jz      short loc_180004875
0x18000485e  lfence
0x180004861  mov     r8d, eax
0x180004864  mov     edx, 16409h
0x180004869  mov     rcx, cs:off_1802601B8; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180004870  call    _bidTraceHR
0x180004875  mov     rbx, cs:?g_pCError@@3PEAVCError@@EA; CError * g_pCError
0x18000487c  test    rbx, rbx
0x18000487f  jz      short loc_1800048A1
0x180004881  mov     rcx, rbx; this
0x180004884  call    ??1CError@@QEAA@XZ; CError::~CError(void)
0x180004889  mov     edx, 40h ; '@'; unsigned __int64
0x18000488e  mov     rcx, rbx; void *
0x180004891  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004896  mov     cs:?g_pCError@@3PEAVCError@@EA, 0; CError * g_pCError
0x1800048a1  xor     eax, eax
0x1800048a3  jmp     short loc_1800048F7
0x1800048a5  mov     rbx, cs:?g_pCError@@3PEAVCError@@EA; CError * g_pCError
0x1800048ac  test    rbx, rbx
0x1800048af  jz      short loc_1800048D1
0x1800048b1  mov     rcx, rbx; this
0x1800048b4  call    ??1CError@@QEAA@XZ; CError::~CError(void)
0x1800048b9  mov     edx, 40h ; '@'; unsigned __int64
0x1800048be  mov     rcx, rbx; void *
0x1800048c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800048c6  mov     cs:?g_pCError@@3PEAVCError@@EA, 0; CError * g_pCError
0x1800048d1  mov     rcx, cs:?g_pMultiLanguage@@3PEAUIMultiLanguage@@EA; IMultiLanguage * g_pMultiLanguage
0x1800048d8  test    rcx, rcx
0x1800048db  jz      short loc_1800048F5
0x1800048dd  mov     rdx, [rcx]
0x1800048e0  mov     rax, [rdx+10h]
0x1800048e4  call    cs:__guard_dispatch_icall_fptr
0x1800048ea  mov     cs:?g_pMultiLanguage@@3PEAUIMultiLanguage@@EA, 0; IMultiLanguage * g_pMultiLanguage
0x1800048f5  mov     eax, esi
0x1800048f7  mov     rcx, [rsp+58h+var_18]
0x1800048fc  xor     rcx, rsp; StackCookie
0x1800048ff  call    __security_check_cookie
0x180004904  mov     rbx, [rsp+58h+arg_0]
0x180004909  add     rsp, 50h
0x18000490d  pop     rsi
0x18000490e  retn
```
