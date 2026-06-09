# System::GetComputerNameExW(_COMPUTER_NAME_FORMAT,FrsStringImpl<ushort,char> &)

- ea: `0x1401c0600`
- end: `0x1401c0777`
- name: `?GetComputerNameExW@System@@SAPEAVFrsStatus@@W4_COMPUTER_NAME_FORMAT@@AEAV?$FrsStringImpl@GD@@@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1401e75e4`

## callees

- `0x140010680`
- `0x140028eec`
- `0x14002c548`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401c0600`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x1401c0635`
- `KERNEL32!GetComputerNameExW` at `0x1401c06e6`
- `KERNEL32!GetComputerNameExW` at `0x1401c0635`
- `KERNEL32!GetComputerNameExW` at `0x1401c06e6`
- `KERNEL32!GetLastError` at `0x1401c0669`
- `KERNEL32!GetLastError` at `0x1401c0704`
- `KERNEL32!GetLastError` at `0x1401c0669`
- `KERNEL32!GetLastError` at `0x1401c0704`
- `KERNEL32!GetCurrentThreadId` at `0x1401c065b`
- `KERNEL32!GetCurrentThreadId` at `0x1401c06f6`
- `KERNEL32!GetCurrentThreadId` at `0x1401c065b`
- `KERNEL32!GetCurrentThreadId` at `0x1401c06f6`

## string_xrefs

- `0x1401c0641`: `System::GetComputerNameExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall System::GetComputerNameExW(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  DWORD v4; // eax
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx
  WCHAR *v8; // rsi
  DWORD v9; // ebx
  DWORD v10; // eax
  __int64 v11; // rcx
  DWORD nSize; // [rsp+70h] [rbp+8h] BYREF
  WCHAR *v14; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  nSize = 0;
  v14 = 0;
  FrsStringImpl<unsigned short,char>::SetEmpty(a2);
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) )
  {
LABEL_4:
    v4 = nSize;
    goto LABEL_5;
  }
  v4 = nSize;
  if ( !nSize )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v3 = FrsStatusList::PushNewError(
           v7,
           LastError,
           0,
           1,
           "base\\fs\\remotefs\\frs\\src\\util\\system.cpp",
           "System::GetComputerNameExW",
           361,
           CurrentThreadId,
           0);
    if ( v3 )
      goto LABEL_8;
    goto LABEL_4;
  }
LABEL_5:
  v8 = (WCHAR *)operator_new(saturated_mul(v4, 2u));
  v14 = v8;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v8, &nSize)
    || (v9 = GetCurrentThreadId(),
        v10 = GetLastError(),
        (v3 = FrsStatusList::PushNewError(
                v11,
                v10,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\system.cpp",
                "System::GetComputerNameExW",
                379,
                v9,
                0)) == 0) )
  {
    FrsStringImpl<unsigned short,char>::Set(a2, v8);
  }
LABEL_8:
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v14);
  return v3;
}

```

## disassembly

```asm
0x1401c0600  mov     rax, rsp
0x1401c0603  mov     [rax+10h], rbx
0x1401c0607  mov     [rax+20h], rsi
0x1401c060b  mov     [rax+8], ecx
0x1401c060e  push    rdi
0x1401c060f  push    r12
0x1401c0611  push    r15
0x1401c0613  sub     rsp, 50h
0x1401c0617  mov     rdi, rdx
0x1401c061a  xor     ebx, ebx
0x1401c061c  and     [rax+8], ebx
0x1401c061f  and     [rax+18h], rbx
0x1401c0623  mov     rcx, rdx
0x1401c0626  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401c062b  lea     r8, [rsp+68h+nSize]; nSize
0x1401c0630  xor     edx, edx; lpBuffer
0x1401c0632  lea     ecx, [rbx+3]; NameType
0x1401c0635  call    cs:__imp_GetComputerNameExW
0x1401c063c  nop     dword ptr [rax+rax+00h]
0x1401c0641  lea     r15, aSystemGetcompu; "System::GetComputerNameExW"
0x1401c0648  lea     r12, aBaseFsRemotefs_67; "base\\fs\\remotefs\\frs\\src\\util\\sys"...
0x1401c064f  test    eax, eax
0x1401c0651  jnz     short loc_1401C06AD
0x1401c0653  mov     eax, [rsp+68h+nSize]
0x1401c0657  test    eax, eax
0x1401c0659  jnz     short loc_1401C06B1
0x1401c065b  call    cs:__imp_GetCurrentThreadId
0x1401c0662  nop     dword ptr [rax+rax+00h]
0x1401c0667  mov     ebx, eax
0x1401c0669  call    cs:__imp_GetLastError
0x1401c0670  nop     dword ptr [rax+rax+00h]
0x1401c0675  and     [rsp+68h+var_28], 0
0x1401c067b  mov     [rsp+68h+var_30], ebx
0x1401c067f  mov     [rsp+68h+var_38], 169h
0x1401c0687  mov     [rsp+68h+var_40], r15
0x1401c068c  mov     [rsp+68h+var_48], r12
0x1401c0691  mov     r9d, 1
0x1401c0697  xor     r8d, r8d
0x1401c069a  mov     edx, eax
0x1401c069c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c06a1  mov     rbx, rax
0x1401c06a4  test    rax, rax
0x1401c06a7  jnz     loc_1401C0750
0x1401c06ad  mov     eax, [rsp+68h+nSize]
0x1401c06b1  mov     edx, eax
0x1401c06b3  mov     eax, 2
0x1401c06b8  mul     rdx
0x1401c06bb  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1401c06c2  cmovo   rax, rdx
0x1401c06c6  mov     rcx, rax; unsigned __int64
0x1401c06c9  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401c06ce  mov     rsi, rax
0x1401c06d1  mov     [rsp+68h+arg_10], rax
0x1401c06d9  lea     r8, [rsp+68h+nSize]; nSize
0x1401c06de  mov     rdx, rax; lpBuffer
0x1401c06e1  mov     ecx, 3; NameType
0x1401c06e6  call    cs:__imp_GetComputerNameExW
0x1401c06ed  nop     dword ptr [rax+rax+00h]
0x1401c06f2  test    eax, eax
0x1401c06f4  jnz     short loc_1401C0744
0x1401c06f6  call    cs:__imp_GetCurrentThreadId
0x1401c06fd  nop     dword ptr [rax+rax+00h]
0x1401c0702  mov     ebx, eax
0x1401c0704  call    cs:__imp_GetLastError
0x1401c070b  nop     dword ptr [rax+rax+00h]
0x1401c0710  and     [rsp+68h+var_28], 0
0x1401c0716  mov     [rsp+68h+var_30], ebx
0x1401c071a  mov     [rsp+68h+var_38], 17Bh
0x1401c0722  mov     [rsp+68h+var_40], r15
0x1401c0727  mov     [rsp+68h+var_48], r12
0x1401c072c  mov     r9d, 1
0x1401c0732  xor     r8d, r8d
0x1401c0735  mov     edx, eax
0x1401c0737  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c073c  mov     rbx, rax
0x1401c073f  test    rax, rax
0x1401c0742  jnz     short loc_1401C0750
0x1401c0744  mov     rdx, rsi
0x1401c0747  mov     rcx, rdi
0x1401c074a  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401c074f  nop
0x1401c0750  lea     rcx, [rsp+68h+arg_10]
0x1401c0758  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1401c075d  mov     rax, rbx
0x1401c0760  lea     r11, [rsp+68h+var_18]
0x1401c0765  mov     rbx, [r11+28h]
0x1401c0769  mov     rsi, [r11+38h]
0x1401c076d  mov     rsp, r11
0x1401c0770  pop     r15
0x1401c0772  pop     r12
0x1401c0774  pop     rdi
0x1401c0775  retn
```
