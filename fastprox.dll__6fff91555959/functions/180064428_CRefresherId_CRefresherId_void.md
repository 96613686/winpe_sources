# CRefresherId::CRefresherId(void)

- ea: `0x180064428`
- end: `0x180064533`
- name: `??0CRefresherId@@QEAA@XZ`
- size: `267`
- prototype: `CRefresherId *__fastcall(CRefresherId *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180064310`

## callees

- `0x180035b08`
- `0x180064428`
- `0x18006fa4c`
- `0x1800919b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800644a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800644a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180064467`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180064467`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800644b6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800644b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006444d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006444d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006449f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006449f`
- `wbemcomn!GetMemLogObject` at `0x1800644d2`
- `wbemcomn!GetMemLogObject` at `0x1800644d2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800644e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800644e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRefresherId *__fastcall CRefresherId::CRefresherId(CRefresherId *this)
{
  LPVOID v2; // rax
  CMemoryLog *MemLogObject; // rax
  char pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-34h] BYREF
  WCHAR Buffer[16]; // [rsp+48h] [rbp-30h] BYREF

  nSize = 16;
  v2 = CoTaskMemAlloc(0x10u);
  *(_QWORD *)this = v2;
  if ( !v2 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids,
        "CX_MemoryException()");
    }
    throw (CX_MemoryException *)&pExceptionObject;
  }
  GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize);
  nSize = WideCharToMultiByte(0, 0x400u, Buffer, -1, *(LPSTR *)this, 16, 0, 0);
  *((_DWORD *)this + 2) = GetCurrentProcessId();
  CoCreateGuid((GUID *)((char *)this + 12));
  return this;
}

```

## disassembly

```asm
0x180064428  push    rbx
0x18006442a  sub     rsp, 70h
0x18006442e  mov     rax, cs:__security_cookie
0x180064435  xor     rax, rsp
0x180064438  mov     [rsp+78h+var_10], rax
0x18006443d  mov     rbx, rcx
0x180064440  mov     [rsp+78h+nSize], 10h
0x180064448  mov     ecx, 10h; cb
0x18006444d  call    cs:__imp_CoTaskMemAlloc
0x180064453  mov     [rbx], rax
0x180064456  test    rax, rax
0x180064459  jz      short loc_1800644D2
0x18006445b  lea     r8, [rsp+78h+nSize]; nSize
0x180064460  xor     ecx, ecx; NameType
0x180064462  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180064467  call    cs:__imp_GetComputerNameExW
0x18006446d  mov     rcx, [rbx]
0x180064470  lea     r8, [rsp+78h+Buffer]; lpWideCharStr
0x180064475  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18006447e  or      r9d, 0FFFFFFFFh; cchWideChar
0x180064482  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18006448b  mov     edx, 400h; dwFlags
0x180064490  mov     [rsp+78h+cbMultiByte], 10h; cbMultiByte
0x180064498  mov     [rsp+78h+lpMultiByteStr], rcx; lpMultiByteStr
0x18006449d  xor     ecx, ecx; CodePage
0x18006449f  call    cs:__imp_WideCharToMultiByte
0x1800644a5  mov     [rsp+78h+nSize], eax
0x1800644a9  call    cs:__imp_GetCurrentProcessId
0x1800644af  lea     rcx, [rbx+0Ch]; pguid
0x1800644b3  mov     [rbx+8], eax
0x1800644b6  call    cs:__imp_CoCreateGuid
0x1800644bc  mov     rax, rbx
0x1800644bf  mov     rcx, [rsp+78h+var_10]
0x1800644c4  xor     rcx, rsp; StackCookie
0x1800644c7  call    __security_check_cookie
0x1800644cc  add     rsp, 70h
0x1800644d0  pop     rbx
0x1800644d1  retn
0x1800644d2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800644d8  mov     rcx, rax
0x1800644db  mov     edx, 0FFFFFFFEh
0x1800644e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800644e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800644ed  lea     rax, WPP_GLOBAL_Control
0x1800644f4  cmp     rcx, rax
0x1800644f7  jz      short loc_180064521
0x1800644f9  test    byte ptr [rcx+1Ch], 1
0x1800644fd  jz      short loc_180064521
0x1800644ff  cmp     byte ptr [rcx+19h], 2
0x180064503  jb      short loc_180064521
0x180064505  mov     rcx, [rcx+10h]
0x180064509  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x180064510  mov     edx, 0Ah
0x180064515  lea     r8, WPP_c58dba40f457377ce3dbee0d04a91c30_Traceguids
0x18006451c  call    WPP_SF_s
0x180064521  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x180064528  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18006452d  call    _CxxThrowException_0
```
