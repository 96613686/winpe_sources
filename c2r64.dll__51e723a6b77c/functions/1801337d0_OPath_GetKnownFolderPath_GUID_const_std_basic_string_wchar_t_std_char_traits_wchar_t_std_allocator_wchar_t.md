# OPath::GetKnownFolderPath(_GUID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1801337d0`
- end: `0x18013391f`
- name: `?GetKnownFolderPath@OPath@@SAXAEBU_GUID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(KNOWNFOLDERID *rfid, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180003694`

## callees

- `0x180009748`
- `0x18000adf0`
- `0x18000b6e0`
- `0x18000c2dc`
- `0x1800277d4`
- `0x18003e690`
- `0x1800409e0`
- `0x18004a468`
- `0x1801337d0`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x180133817`
- `SHELL32!SHGetKnownFolderPath` at `0x18013383b`
- `SHELL32!SHGetKnownFolderPath` at `0x180133817`
- `SHELL32!SHGetKnownFolderPath` at `0x18013383b`
- `ole32!CoTaskMemFree` at `0x1801338f5`
- `ole32!CoTaskMemFree` at `0x1801338f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall OPath::GetKnownFolderPath(KNOWNFOLDERID *rfid, void *a2)
{
  PWSTR v4; // rdx
  __int64 v5; // rax
  PWSTR v6; // rcx
  PWSTR ppszPath; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v8[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v9[40]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+70h] [rbp-90h] BYREF

  ppszPath = 0;
  if ( SHGetKnownFolderPath(rfid, 0x400u, 0, &ppszPath) >= 0 && (v4 = ppszPath) != 0
    || SHGetKnownFolderPath(rfid, 0xC400u, 0, &ppszPath) >= 0 && (v4 = ppszPath) != 0 )
  {
    std::wstring::assign(a2, v4);
  }
  else
  {
    v5 = *(_QWORD *)&rfid->Data1 - *(_QWORD *)&FOLDERID_ProgramData.Data1;
    if ( *(_QWORD *)&rfid->Data1 == *(_QWORD *)&FOLDERID_ProgramData.Data1 )
      v5 = *(_QWORD *)rfid->Data4 - *(_QWORD *)FOLDERID_ProgramData.Data4;
    if ( v5 )
    {
      OException::OException(pExceptionObject, 34, L"Unable to get folder for rfid.");
      throw (OException *)pExceptionObject;
    }
    std::wstring::wstring(v8, L"%ALLUSERSPROFILE%");
    OEnvironment::ExpandEnvironmentVariables(v9, v8);
    std::wstring::operator=(a2);
    std::wstring::~wstring(v9);
    std::wstring::~wstring(v8);
  }
  v6 = ppszPath;
  if ( ppszPath )
  {
    ppszPath = 0;
    CoTaskMemFree(v6);
  }
}

```

## disassembly

```asm
0x1801337d0  mov     [rsp-8+arg_10], rbx
0x1801337d5  mov     [rsp-8+arg_18], rdi
0x1801337da  push    rbp
0x1801337db  lea     rbp, [rsp-310h]
0x1801337e3  sub     rsp, 410h
0x1801337ea  mov     rax, cs:__security_cookie
0x1801337f1  xor     rax, rsp
0x1801337f4  mov     [rbp+310h+var_10], rax
0x1801337fb  mov     rdi, rdx
0x1801337fe  mov     rbx, rcx
0x180133801  mov     [rsp+410h+ppszPath], 0
0x18013380a  lea     r9, [rsp+410h+ppszPath]; ppszPath
0x18013380f  xor     r8d, r8d; hToken
0x180133812  mov     edx, 400h; dwFlags
0x180133817  call    cs:__imp_SHGetKnownFolderPath
0x18013381d  test    eax, eax
0x18013381f  js      short loc_18013382B
0x180133821  mov     rdx, [rsp+410h+ppszPath]
0x180133826  test    rdx, rdx
0x180133829  jnz     short loc_18013384F
0x18013382b  lea     r9, [rsp+410h+ppszPath]; ppszPath
0x180133830  xor     r8d, r8d; hToken
0x180133833  mov     edx, 0C400h; dwFlags
0x180133838  mov     rcx, rbx; rfid
0x18013383b  call    cs:__imp_SHGetKnownFolderPath
0x180133841  test    eax, eax
0x180133843  js      short loc_18013385C
0x180133845  mov     rdx, [rsp+410h+ppszPath]; Src
0x18013384a  test    rdx, rdx
0x18013384d  jz      short loc_18013385C
0x18013384f  mov     rcx, rdi; void *
0x180133852  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180133857  jmp     loc_1801338E2
0x18013385c  mov     rax, [rbx]
0x18013385f  sub     rax, qword ptr cs:FOLDERID_ProgramData.Data1
0x180133866  jnz     short loc_180133873
0x180133868  mov     rax, [rbx+8]
0x18013386c  sub     rax, qword ptr cs:FOLDERID_ProgramData.Data4
0x180133873  test    rax, rax
0x180133876  jz      short loc_1801338A0
0x180133878  lea     r8, aUnableToGetFol; "Unable to get folder for rfid."
0x18013387f  mov     edx, 22h ; '"'
0x180133884  lea     rcx, [rsp+410h+pExceptionObject]
0x180133889  call    ??$?0$0BP@@OException@@QEAA@W4exceptionType@et@@AEAY0BP@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[31])
0x18013388e  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180133895  lea     rcx, [rsp+410h+pExceptionObject]; pExceptionObject
0x18013389a  call    _CxxThrowException
0x1801338a0  lea     rdx, aAllusersprofil; "%ALLUSERSPROFILE%"
0x1801338a7  lea     rcx, [rsp+410h+var_3E8]
0x1801338ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801338b1  nop
0x1801338b2  lea     rdx, [rsp+410h+var_3E8]
0x1801338b7  lea     rcx, [rsp+410h+var_3C8]
0x1801338bc  call    ?ExpandEnvironmentVariables@OEnvironment@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@Z; OEnvironment::ExpandEnvironmentVariables(std::wstring const &)
0x1801338c1  mov     rdx, rax
0x1801338c4  mov     rcx, rdi
0x1801338c7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801338cc  lea     rcx, [rsp+410h+var_3C8]; void *
0x1801338d1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801338d6  nop
0x1801338d7  lea     rcx, [rsp+410h+var_3E8]; void *
0x1801338dc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801338e1  nop
0x1801338e2  mov     rcx, [rsp+410h+ppszPath]; pv
0x1801338e7  test    rcx, rcx
0x1801338ea  jz      short loc_1801338FB
0x1801338ec  mov     [rsp+410h+ppszPath], 0
0x1801338f5  call    cs:__imp_CoTaskMemFree
0x1801338fb  mov     rcx, [rbp+310h+var_10]
0x180133902  xor     rcx, rsp; StackCookie
0x180133905  call    __security_check_cookie
0x18013390a  lea     r11, [rsp+410h+var_s0]
0x180133912  mov     rbx, [r11+20h]
0x180133916  mov     rdi, [r11+28h]
0x18013391a  mov     rsp, r11
0x18013391d  pop     rbp
0x18013391e  retn
```
