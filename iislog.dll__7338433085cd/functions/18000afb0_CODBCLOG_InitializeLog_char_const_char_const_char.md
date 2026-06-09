# CODBCLOG::InitializeLog(char const *,char const *,char *)

- ea: `0x18000afb0`
- end: `0x18000b115`
- name: `?InitializeLog@CODBCLOG@@UEAAJPEBD0PEAD@Z`
- size: `357`
- prototype: `__int64 __fastcall(CODBCLOG *__hidden this, const char *, const char *, char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x18000a978`
- `0x18000ab80`
- `0x18000afb0`
- `0x18000ba58`
- `0x18000bc18`
- `0x18000e300`

## import_xrefs

- `msvcrt!_strnicmp` at `0x18000b01b`
- `msvcrt!_strnicmp` at `0x18000b01b`
- `msvcrt!strncpy_s` at `0x18000b005`
- `msvcrt!strncpy_s` at `0x18000b005`
- `KERNEL32!EnterCriticalSection` at `0x18000b059`
- `KERNEL32!EnterCriticalSection` at `0x18000b059`
- `KERNEL32!LeaveCriticalSection` at `0x18000b0e7`
- `KERNEL32!LeaveCriticalSection` at `0x18000b0e7`
- `KERNEL32!GetLastError` at `0x18000b0c9`
- `KERNEL32!GetLastError` at `0x18000b0c9`
- `KERNEL32!GetComputerNameA` at `0x18000afe4`
- `KERNEL32!GetComputerNameA` at `0x18000afe4`

## pseudocode

```c
__int64 __fastcall CODBCLOG::InitializeLog(CODBCLOG *this, const char *a2, const char *a3, char *a4)
{
  _BYTE *v4; // r14
  signed int RegParametersFromNativeConfig; // eax
  DWORD LastError; // ebx
  bool v11; // cc
  _WORD *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // r8d
  DWORD v16; // [rsp+50h] [rbp+8h] BYREF

  v4 = (char *)this + 1189;
  v16 = 261;
  if ( !GetComputerNameA((LPSTR)this + 1189, &v16) )
    *v4 = 0;
  strncpy_s((char *)this + 928, 0x105u, a2, 0x103u);
  if ( !_strnicmp(a2, "w3svc", 5u) )
    RegParametersFromNativeConfig = CODBCLOG::GetRegParametersFromNativeConfig(this, a2, a4);
  else
    RegParametersFromNativeConfig = CODBCLOG::GetRegParameters(this, a3, a4);
  LastError = RegParametersFromNativeConfig;
  v11 = RegParametersFromNativeConfig <= 0;
  if ( RegParametersFromNativeConfig )
    goto LABEL_16;
  if ( *((_QWORD *)this + 113) )
    return 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v12 = operator new(0x18u);
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    v12[8] = 0;
    *((_DWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)this + 113) = v12;
    if ( !(unsigned int)ODBC_CONNECTION::Open(
                          (ODBC_CONNECTION *)v12,
                          (SQLCHAR *)this + 96,
                          (SQLCHAR *)this + 386,
                          (SQLCHAR *)this + 643,
                          1)
      || !(unsigned int)CODBCLOG::PrepareStatement(this, v13, v14)
      || !(unsigned int)CODBCLOG::PrepareParameters((void ***)this) )
    {
      LastError = GetLastError();
    }
  }
  else
  {
    *((_QWORD *)this + 113) = 0;
    LastError = 8;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v11 = (int)LastError <= 0;
  if ( LastError )
  {
LABEL_16:
    if ( !v11 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000afb0  mov     rax, rsp
0x18000afb3  mov     [rax+10h], rbx
0x18000afb7  mov     [rax+18h], rbp
0x18000afbb  push    rsi
0x18000afbc  push    rdi
0x18000afbd  push    r14
0x18000afbf  sub     rsp, 30h
0x18000afc3  lea     r14, [rcx+4A5h]
0x18000afca  mov     dword ptr [rax+8], 105h
0x18000afd1  mov     rsi, rdx
0x18000afd4  mov     rdi, rcx
0x18000afd7  mov     rcx, r14; lpBuffer
0x18000afda  lea     rdx, [rax+8]; nSize
0x18000afde  mov     rbx, r9
0x18000afe1  mov     rbp, r8
0x18000afe4  call    cs:__imp_GetComputerNameA
0x18000afea  test    eax, eax
0x18000afec  jnz     short loc_18000AFF1
0x18000afee  mov     [r14], al
0x18000aff1  mov     r9d, 103h; MaxCount
0x18000aff7  lea     rcx, [rdi+3A0h]; Destination
0x18000affe  mov     r8, rsi; Source
0x18000b001  lea     edx, [r9+2]; SizeInBytes
0x18000b005  call    cs:__imp_strncpy_s
0x18000b00b  mov     r8d, 5; MaxCount
0x18000b011  lea     rdx, aW3svc; "w3svc"
0x18000b018  mov     rcx, rsi; String1
0x18000b01b  call    cs:__imp__strnicmp
0x18000b021  mov     r8, rbx; void *
0x18000b024  mov     rcx, rdi; this
0x18000b027  test    eax, eax
0x18000b029  jnz     short loc_18000B035
0x18000b02b  mov     rdx, rsi; char *
0x18000b02e  call    ?GetRegParametersFromNativeConfig@CODBCLOG@@QEAAKPEBDPEAX@Z; CODBCLOG::GetRegParametersFromNativeConfig(char const *,void *)
0x18000b033  jmp     short loc_18000B03D
0x18000b035  mov     rdx, rbp; char *
0x18000b038  call    ?GetRegParameters@CODBCLOG@@QEAAKPEBDPEAX@Z; CODBCLOG::GetRegParameters(char const *,void *)
0x18000b03d  mov     ebx, eax
0x18000b03f  test    eax, eax
0x18000b041  jnz     loc_18000B0F5
0x18000b047  cmp     qword ptr [rdi+388h], 0
0x18000b04f  jnz     loc_18000B0F1
0x18000b055  lea     rcx, [rdi+38h]; lpCriticalSection
0x18000b059  call    cs:__imp_EnterCriticalSection
0x18000b05f  lea     ecx, [rbx+18h]; Size
0x18000b062  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b067  test    rax, rax
0x18000b06a  jz      short loc_18000B0D3
0x18000b06c  xor     ecx, ecx
0x18000b06e  mov     qword ptr [rax], 0
0x18000b075  mov     [rax+10h], cx
0x18000b079  lea     r9, [rdi+283h]; Authentication
0x18000b080  mov     [rax+14h], ecx
0x18000b083  lea     r8, [rdi+182h]; UserName
0x18000b08a  mov     qword ptr [rax+8], 0
0x18000b092  lea     rdx, [rdi+60h]; ServerName
0x18000b096  mov     rcx, rax; this
0x18000b099  mov     [rdi+388h], rax
0x18000b0a0  mov     [rsp+48h+var_28], 1; int
0x18000b0a8  call    ?Open@ODBC_CONNECTION@@QEAAHPEBD00H@Z; ODBC_CONNECTION::Open(char const *,char const *,char const *,int)
0x18000b0ad  test    eax, eax
0x18000b0af  jz      short loc_18000B0C9
0x18000b0b1  mov     rcx, rdi; this
0x18000b0b4  call    ?PrepareStatement@CODBCLOG@@QEAAHXZ; CODBCLOG::PrepareStatement(void)
0x18000b0b9  test    eax, eax
0x18000b0bb  jz      short loc_18000B0C9
0x18000b0bd  mov     rcx, rdi; this
0x18000b0c0  call    ?PrepareParameters@CODBCLOG@@QEAAHXZ; CODBCLOG::PrepareParameters(void)
0x18000b0c5  test    eax, eax
0x18000b0c7  jnz     short loc_18000B0E3
0x18000b0c9  call    cs:__imp_GetLastError
0x18000b0cf  mov     ebx, eax
0x18000b0d1  jmp     short loc_18000B0E3
0x18000b0d3  mov     qword ptr [rdi+388h], 0
0x18000b0de  mov     ebx, 8
0x18000b0e3  lea     rcx, [rdi+38h]; lpCriticalSection
0x18000b0e7  call    cs:__imp_LeaveCriticalSection
0x18000b0ed  test    ebx, ebx
0x18000b0ef  jnz     short loc_18000B0F5
0x18000b0f1  xor     ebx, ebx
0x18000b0f3  jmp     short loc_18000B100
0x18000b0f5  jle     short loc_18000B100
0x18000b0f7  movzx   ebx, bx
0x18000b0fa  or      ebx, 80070000h
0x18000b100  mov     rbp, [rsp+48h+arg_10]
0x18000b105  mov     eax, ebx
0x18000b107  mov     rbx, [rsp+48h+arg_8]
0x18000b10c  add     rsp, 30h
0x18000b110  pop     r14
0x18000b112  pop     rdi
0x18000b113  pop     rsi
0x18000b114  retn
```
