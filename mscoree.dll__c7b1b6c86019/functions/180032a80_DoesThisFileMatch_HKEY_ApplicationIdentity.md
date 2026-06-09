# DoesThisFileMatch(HKEY__ *,ApplicationIdentity *)

- ea: `0x180032a80`
- end: `0x180032bfa`
- name: `?DoesThisFileMatch@@YAHPEAUHKEY__@@PEAVApplicationIdentity@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(HKEY hKey, struct ApplicationIdentity *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003070`
- `0x18000aee8`
- `0x18000b1f0`
- `0x18000d434`
- `0x1800324d8`
- `0x1800324f8`
- `0x1800325d4`
- `0x180032a80`
- `0x180033304`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x180032b40`
- `KERNEL32!GetFileAttributesExW` at `0x180032b40`

## string_xrefs

- `0x180032adc`: `File Path`
- `0x180032b79`: `%s is not a relative path!`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 __fastcall DoesThisFileMatch(HKEY hKey, const wchar_t **this)
{
  int RegistryStringValue; // eax
  int v5; // ecx
  unsigned __int16 *v6; // rbx
  BOOL v7; // ebx
  unsigned __int16 *v9; // [rsp+20h] [rbp-89h] BYREF
  int v10; // [rsp+28h] [rbp-81h]
  unsigned __int16 *v11; // [rsp+30h] [rbp-79h] BYREF
  int v12; // [rsp+38h] [rbp-71h]
  unsigned __int16 **v13; // [rsp+40h] [rbp-69h]
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-61h] BYREF
  int v15; // [rsp+68h] [rbp-41h]
  wchar_t *String1[14]; // [rsp+70h] [rbp-39h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = &v9;
  RegistryStringValue = GetRegistryStringValue(hKey, L"File Path", (BYTE **)&v9);
  v5 = v10;
  if ( v9 )
    v5 = 1;
  v10 = v5;
  if ( !RegistryStringValue
    && (v6 = ApplicationIdentity::AddFullPathToRelativeFile((ApplicationIdentity *)this, v9), (v11 = v6) != 0)
    && (v12 = 1,
        memset(FileInformation, 0, sizeof(FileInformation)),
        v15 = 0,
        GetFileAttributesExW(v6, GetFileExInfoStandard, FileInformation)) )
  {
    ApplicationIdentity::ApplicationIdentity((ApplicationIdentity *)String1, v6);
    if ( wcsnicmp(String1[0], *this, (unsigned int)(this[1] - *this)) )
    {
      ReportAppCompatError((wchar_t *)L"%s is not a relative path!", v9);
      v7 = 0;
    }
    else
    {
      v7 = DoesThisAppMatch(String1, hKey) == 0;
    }
    ApplicationIdentity::~ApplicationIdentity((ApplicationIdentity *)String1);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v11);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v9);
    return v7;
  }
  else
  {
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v11);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v9);
    return 0;
  }
}

```

## disassembly

```asm
0x180032a80  mov     [rsp-8+arg_10], rbx
0x180032a85  mov     [rsp-8+arg_18], rsi
0x180032a8a  push    rbp
0x180032a8b  push    rdi
0x180032a8c  push    r15
0x180032a8e  lea     rbp, [rsp-47h]
0x180032a93  sub     rsp, 0F0h
0x180032a9a  mov     rax, cs:__security_cookie
0x180032aa1  xor     rax, rsp
0x180032aa4  mov     [rbp+57h+var_20], rax
0x180032aa8  mov     rdi, rdx
0x180032aab  mov     rsi, rcx
0x180032aae  mov     [rsp+100h+var_E0], 0
0x180032ab7  mov     [rsp+100h+var_D8], 0
0x180032abf  mov     [rbp+57h+var_D0], 0
0x180032ac7  mov     [rbp+57h+var_C8], 0
0x180032ace  lea     rax, [rsp+100h+var_E0]
0x180032ad3  mov     [rbp+57h+var_C0], rax
0x180032ad7  lea     r8, [rsp+100h+var_E0]; unsigned __int16 **
0x180032adc  lea     rdx, aFilePath; "File Path"
0x180032ae3  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180032ae8  nop
0x180032ae9  mov     ecx, [rsp+100h+var_D8]
0x180032aed  mov     r15d, 1
0x180032af3  mov     rdx, [rsp+100h+var_E0]; unsigned __int16 *
0x180032af8  test    rdx, rdx
0x180032afb  cmovnz  ecx, r15d
0x180032aff  mov     [rsp+100h+var_D8], ecx
0x180032b03  test    eax, eax
0x180032b05  jnz     loc_180032BC0
0x180032b0b  mov     rcx, rdi; this
0x180032b0e  call    ?AddFullPathToRelativeFile@ApplicationIdentity@@QEAAPEAGPEAG@Z; ApplicationIdentity::AddFullPathToRelativeFile(ushort *)
0x180032b13  mov     rbx, rax
0x180032b16  mov     [rbp+57h+var_D0], rax
0x180032b1a  test    rax, rax
0x180032b1d  jz      loc_180032BC0
0x180032b23  mov     [rbp+57h+var_C8], r15d
0x180032b27  xorps   xmm0, xmm0
0x180032b2a  xor     eax, eax
0x180032b2c  movups  [rbp+57h+FileInformation], xmm0
0x180032b30  movups  [rbp+57h+var_A8], xmm0
0x180032b34  mov     [rbp+57h+var_98], eax
0x180032b37  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180032b3b  xor     edx, edx; fInfoLevelId
0x180032b3d  mov     rcx, rbx; lpFileName
0x180032b40  call    cs:__imp_GetFileAttributesExW
0x180032b46  test    eax, eax
0x180032b48  jz      short loc_180032BC0
0x180032b4a  mov     rdx, rbx; unsigned __int16 *
0x180032b4d  lea     rcx, [rbp+57h+String1]; this
0x180032b51  call    ??0ApplicationIdentity@@QEAA@PEAG@Z; ApplicationIdentity::ApplicationIdentity(ushort *)
0x180032b56  nop
0x180032b57  mov     r8, [rdi+8]
0x180032b5b  sub     r8, [rdi]
0x180032b5e  sar     r8, 1
0x180032b61  mov     r8d, r8d; MaxCount
0x180032b64  mov     rdx, [rdi]; String2
0x180032b67  mov     rcx, [rbp+57h+String1]; String1
0x180032b6b  call    _wcsnicmp
0x180032b70  test    eax, eax
0x180032b72  jz      short loc_180032B8A
0x180032b74  mov     rdx, [rsp+100h+var_E0]
0x180032b79  lea     rcx, aSIsNotARelativ; "%s is not a relative path!"
0x180032b80  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x180032b85  nop
0x180032b86  xor     ebx, ebx
0x180032b88  jmp     short loc_180032B9E
0x180032b8a  mov     rdx, rsi; hKey
0x180032b8d  lea     rcx, [rbp+57h+String1]; this
0x180032b91  call    ?DoesThisAppMatch@@YAJPEAVApplicationIdentity@@PEAUHKEY__@@@Z; DoesThisAppMatch(ApplicationIdentity *,HKEY__ *)
0x180032b96  nop
0x180032b97  xor     ebx, ebx
0x180032b99  test    eax, eax
0x180032b9b  setz    bl
0x180032b9e  lea     rcx, [rbp+57h+String1]; this
0x180032ba2  call    ??1ApplicationIdentity@@QEAA@XZ; ApplicationIdentity::~ApplicationIdentity(void)
0x180032ba7  nop
0x180032ba8  lea     rcx, [rbp+57h+var_D0]
0x180032bac  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032bb1  nop
0x180032bb2  lea     rcx, [rsp+100h+var_E0]
0x180032bb7  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032bbc  mov     eax, ebx
0x180032bbe  jmp     short loc_180032BD6
0x180032bc0  lea     rcx, [rbp+57h+var_D0]
0x180032bc4  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032bc9  nop
0x180032bca  lea     rcx, [rsp+100h+var_E0]
0x180032bcf  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032bd4  xor     eax, eax
0x180032bd6  mov     rcx, [rbp+57h+var_20]
0x180032bda  xor     rcx, rsp; StackCookie
0x180032bdd  call    __security_check_cookie
0x180032be2  lea     r11, [rsp+100h+var_10]
0x180032bea  mov     rbx, [r11+30h]
0x180032bee  mov     rsi, [r11+38h]
0x180032bf2  mov     rsp, r11
0x180032bf5  pop     r15
0x180032bf7  pop     rdi
0x180032bf8  pop     rbp
0x180032bf9  retn
```
