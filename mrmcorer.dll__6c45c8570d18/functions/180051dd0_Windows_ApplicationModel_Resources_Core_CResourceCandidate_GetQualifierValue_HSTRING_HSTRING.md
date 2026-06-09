# Windows::ApplicationModel::Resources::Core::CResourceCandidate::GetQualifierValue(HSTRING__ *,HSTRING__ * *)

- ea: `0x180051dd0`
- end: `0x180051ec2`
- name: `?GetQualifierValue@CResourceCandidate@Core@Resources@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU6@@Z`
- size: `242`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceCandidate *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002c8d0`
- `0x180051dd0`
- `0x180051f6c`
- `0x1800521bc`
- `0x18006997c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180051dfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180051dfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051e62`

## string_xrefs

- `0x180051e48`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`
- `0x180051e8b`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecandidate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceCandidate::GetQualifierValue(
        Windows::ApplicationModel::Resources::Core::CResourceCandidate *this,
        HSTRING a2,
        HSTRING *a3)
{
  Microsoft::Resources::Runtime::CResolvedInstanceInternal *v4; // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 result; // rax
  unsigned int v7; // ebx
  HSTRING v8; // rbx
  int v9; // edi
  HSTRING string; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int16 *v11; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a3 = 0;
  v11 = 0;
  v4 = (Microsoft::Resources::Runtime::CResolvedInstanceInternal *)*((_QWORD *)this + 10);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  result = Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetConditionValue(
             v4,
             StringRawBuffer,
             (const unsigned __int16 **)&v11);
  v7 = result;
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result != -2147023727 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
        (const char *)(unsigned int)result,
        (int)string);
      return v7;
    }
  }
  else
  {
    v8 = 0;
    string = 0;
    if ( v11 )
    {
      v9 = Windows::Internal::String::_InitializeHelper(&string, v11);
      if ( v9 >= 0 )
      {
        *a3 = string;
        string = 0;
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        return 0;
      }
      v8 = string;
    }
    else
    {
      v9 = -2147467261;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE9,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecandidate.cpp",
      (const char *)(unsigned int)v9,
      (int)string);
    if ( v8 )
      WindowsDeleteString(v8);
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x180051dd0  mov     [rsp+arg_8], rbx
0x180051dd5  mov     [rsp+arg_18], rsi
0x180051dda  push    rdi
0x180051ddb  sub     rsp, 30h
0x180051ddf  mov     rsi, r8
0x180051de2  mov     rax, rdx
0x180051de5  mov     qword ptr [r8], 0
0x180051dec  mov     [rsp+38h+var_10], 0
0x180051df5  mov     rbx, [rcx+50h]
0x180051df9  xor     edx, edx; length
0x180051dfb  mov     rcx, rax; string
0x180051dfe  call    cs:__imp_WindowsGetStringRawBuffer
0x180051e04  lea     r8, [rsp+38h+var_10]; unsigned __int16 **
0x180051e09  mov     rdx, rax; lpString1
0x180051e0c  mov     rcx, rbx; this
0x180051e0f  call    ?GetConditionValue@CResolvedInstanceInternal@Runtime@Resources@Microsoft@@QEBAJPEBGPEAPEBG@Z; Microsoft::Resources::Runtime::CResolvedInstanceInternal::GetConditionValue(ushort const *,ushort const * *)
0x180051e14  mov     ebx, eax
0x180051e16  test    eax, eax
0x180051e18  js      short loc_180051E7B
0x180051e1a  xor     ebx, ebx
0x180051e1c  mov     [rsp+38h+string], rbx; int
0x180051e21  mov     rdx, [rsp+38h+var_10]; unsigned __int16 *
0x180051e26  test    rdx, rdx
0x180051e29  jz      short loc_180051EA0
0x180051e2b  lea     rcx, [rsp+38h+string]; this
0x180051e30  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180051e35  mov     edi, eax
0x180051e37  test    eax, eax
0x180051e39  jns     short loc_180051EA7
0x180051e3b  mov     rbx, [rsp+38h+string]
0x180051e40  mov     rcx, [rsp+38h]; this
0x180051e45  mov     r9d, edi; char *
0x180051e48  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180051e4f  mov     edx, 0E9h; void *
0x180051e54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051e59  nop
0x180051e5a  test    rbx, rbx
0x180051e5d  jz      short loc_180051E69
0x180051e5f  mov     rcx, rbx; string
0x180051e62  call    cs:__imp_WindowsDeleteString
0x180051e68  nop
0x180051e69  mov     eax, edi
0x180051e6b  mov     rbx, [rsp+38h+arg_8]
0x180051e70  mov     rsi, [rsp+38h+arg_18]
0x180051e75  add     rsp, 30h
0x180051e79  pop     rdi
0x180051e7a  retn
0x180051e7b  cmp     ebx, 80070491h
0x180051e81  jz      short loc_180051E6B
0x180051e83  mov     rcx, [rsp+38h]; this
0x180051e88  mov     r9d, ebx; char *
0x180051e8b  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180051e92  mov     edx, 0E6h; void *
0x180051e97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051e9c  mov     eax, ebx
0x180051e9e  jmp     short loc_180051E6B
0x180051ea0  mov     edi, 80004003h
0x180051ea5  jmp     short loc_180051E40
0x180051ea7  mov     rax, [rsp+38h+string]
0x180051eac  mov     [rsi], rax
0x180051eaf  mov     [rsp+38h+string], rbx
0x180051eb4  lea     rcx, [rsp+38h+string]; this
0x180051eb9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180051ebe  xor     eax, eax
0x180051ec0  jmp     short loc_180051E6B
```
