# System::GetComputerObjectNameW(EXTENDED_NAME_FORMAT,FrsStringImpl<ushort,char> &)

- ea: `0x1401c085c`
- end: `0x1401c09cb`
- name: `?GetComputerObjectNameW@System@@SAPEAVFrsStatus@@W4EXTENDED_NAME_FORMAT@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `367`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1401e4fa8`
- `0x1401f8f08`

## callees

- `0x140010680`
- `0x140028eec`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c085c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c08ba`
- `KERNEL32!GetLastError` at `0x1401c0931`
- `KERNEL32!GetLastError` at `0x1401c08ba`
- `KERNEL32!GetLastError` at `0x1401c0931`
- `KERNEL32!GetCurrentThreadId` at `0x1401c0923`
- `KERNEL32!GetCurrentThreadId` at `0x1401c0953`
- `KERNEL32!GetCurrentThreadId` at `0x1401c0923`
- `KERNEL32!GetCurrentThreadId` at `0x1401c0953`
- `Secur32!GetComputerObjectNameW` at `0x1401c08a6`
- `Secur32!GetComputerObjectNameW` at `0x1401c0913`
- `Secur32!GetComputerObjectNameW` at `0x1401c08a6`
- `Secur32!GetComputerObjectNameW` at `0x1401c0913`

## string_xrefs

- `0x1401c0973`: `System::GetComputerObjectNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall System::GetComputerObjectNameW(ULONG a1, __int64 a2)
{
  __int64 v3; // rdi
  WCHAR *v4; // rbx
  DWORD LastError; // esi
  WCHAR *v6; // rsi
  DWORD CurrentThreadId; // edi
  __int64 v8; // rdx
  __int64 v9; // rax
  DWORD v11; // [rsp+38h] [rbp-30h]
  ULONG nSize; // [rsp+70h] [rbp+8h] BYREF
  WCHAR *v13; // [rsp+80h] [rbp+18h] BYREF

  nSize = a1;
  v3 = 0;
  v13 = 0;
  FrsStringImpl<unsigned short,char>::SetEmpty(a2);
  nSize = 1024;
  v4 = (WCHAR *)operator_new(0x800u);
  v13 = v4;
  if ( GetComputerObjectNameW(NameFullyQualifiedDN, v4, &nSize) )
    goto LABEL_9;
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v6 = (WCHAR *)operator_new(saturated_mul(nSize, 2u));
    if ( v4 != v6 )
    {
      operator delete[](v4);
      v4 = v6;
      v13 = v6;
    }
    if ( GetComputerObjectNameW(NameFullyQualifiedDN, v4, &nSize) )
      goto LABEL_9;
    CurrentThreadId = GetCurrentThreadId();
    v8 = GetLastError();
    v9 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\system.cpp",
           v8,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\system.cpp",
           "System::GetComputerObjectNameW",
           477,
           CurrentThreadId,
           0);
  }
  else
  {
    v11 = GetCurrentThreadId();
    v9 = FrsStatusList::PushNewError(
           "base\\fs\\remotefs\\frs\\src\\util\\system.cpp",
           LastError,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\system.cpp",
           "System::GetComputerObjectNameW",
           487,
           v11,
           0);
  }
  v3 = v9;
  if ( !v9 )
LABEL_9:
    FrsStringImpl<unsigned short,char>::Set(a2, v4);
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v13);
  return v3;
}

```

## disassembly

```asm
0x1401c085c  mov     rax, rsp
0x1401c085f  mov     [rax+10h], rbx
0x1401c0863  mov     [rax+8], ecx
0x1401c0866  push    rbp
0x1401c0867  push    rsi
0x1401c0868  push    rdi
0x1401c0869  sub     rsp, 50h
0x1401c086d  mov     rbp, rdx
0x1401c0870  xor     edi, edi
0x1401c0872  and     [rax+18h], rdi
0x1401c0876  mov     rcx, rdx
0x1401c0879  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401c087e  mov     [rsp+68h+nSize], 400h
0x1401c0886  mov     ecx, 800h; unsigned __int64
0x1401c088b  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c0890  mov     rbx, rax
0x1401c0893  mov     [rsp+68h+arg_10], rax
0x1401c089b  lea     r8, [rsp+68h+nSize]; nSize
0x1401c08a0  mov     rdx, rax; lpNameBuffer
0x1401c08a3  lea     ecx, [rdi+1]; NameFormat
0x1401c08a6  call    cs:__imp_GetComputerObjectNameW
0x1401c08ad  nop     dword ptr [rax+rax+00h]
0x1401c08b2  test    al, al
0x1401c08b4  jnz     loc_1401C09A1
0x1401c08ba  call    cs:__imp_GetLastError
0x1401c08c1  nop     dword ptr [rax+rax+00h]
0x1401c08c6  mov     esi, eax
0x1401c08c8  cmp     eax, 7Ah ; 'z'
0x1401c08cb  jnz     loc_1401C0953
0x1401c08d1  mov     ecx, [rsp+68h+nSize]
0x1401c08d5  lea     eax, [rdi+2]
0x1401c08d8  mul     rcx
0x1401c08db  lea     rcx, [rdi-1]
0x1401c08df  cmovo   rax, rcx
0x1401c08e3  mov     rcx, rax; unsigned __int64
0x1401c08e6  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c08eb  mov     rsi, rax
0x1401c08ee  cmp     rbx, rax
0x1401c08f1  jz      short loc_1401C0906
0x1401c08f3  mov     rcx, rbx; Block
0x1401c08f6  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c08fb  mov     rbx, rsi
0x1401c08fe  mov     [rsp+68h+arg_10], rbx
0x1401c0906  lea     r8, [rsp+68h+nSize]; nSize
0x1401c090b  mov     rdx, rbx; lpNameBuffer
0x1401c090e  mov     ecx, 1; NameFormat
0x1401c0913  call    cs:__imp_GetComputerObjectNameW
0x1401c091a  nop     dword ptr [rax+rax+00h]
0x1401c091f  test    al, al
0x1401c0921  jnz     short loc_1401C09A1
0x1401c0923  call    cs:__imp_GetCurrentThreadId
0x1401c092a  nop     dword ptr [rax+rax+00h]
0x1401c092f  mov     edi, eax
0x1401c0931  call    cs:__imp_GetLastError
0x1401c0938  nop     dword ptr [rax+rax+00h]
0x1401c093d  and     [rsp+68h+var_28], 0
0x1401c0943  mov     [rsp+68h+var_30], edi
0x1401c0947  mov     [rsp+68h+var_38], 1DDh
0x1401c094f  mov     edx, eax
0x1401c0951  jmp     short loc_1401C0973
0x1401c0953  call    cs:__imp_GetCurrentThreadId
0x1401c095a  nop     dword ptr [rax+rax+00h]
0x1401c095f  and     [rsp+68h+var_28], 0
0x1401c0965  mov     [rsp+68h+var_30], eax
0x1401c0969  mov     [rsp+68h+var_38], 1E7h
0x1401c0971  mov     edx, esi
0x1401c0973  lea     rcx, aSystemGetcompu_1; "System::GetComputerObjectNameW"
0x1401c097a  mov     [rsp+68h+var_40], rcx
0x1401c097f  lea     rcx, aBaseFsRemotefs_67; "base\\fs\\remotefs\\frs\\src\\util\\sys"...
0x1401c0986  mov     [rsp+68h+var_48], rcx
0x1401c098b  mov     r9d, 1
0x1401c0991  xor     r8d, r8d
0x1401c0994  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c0999  mov     rdi, rax
0x1401c099c  test    rax, rax
0x1401c099f  jnz     short loc_1401C09AD
0x1401c09a1  mov     rdx, rbx
0x1401c09a4  mov     rcx, rbp
0x1401c09a7  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401c09ac  nop
0x1401c09ad  lea     rcx, [rsp+68h+arg_10]
0x1401c09b5  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401c09ba  mov     rax, rdi
0x1401c09bd  mov     rbx, [rsp+68h+arg_8]
0x1401c09c2  add     rsp, 50h
0x1401c09c6  pop     rdi
0x1401c09c7  pop     rsi
0x1401c09c8  pop     rbp
0x1401c09c9  retn
```
