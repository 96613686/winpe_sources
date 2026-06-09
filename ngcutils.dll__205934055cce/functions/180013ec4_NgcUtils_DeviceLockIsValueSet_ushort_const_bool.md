# NgcUtils::DeviceLockIsValueSet(ushort const *,bool *)

- ea: `0x180013ec4`
- end: `0x180013fdc`
- name: `?DeviceLockIsValueSet@NgcUtils@@YAJPEBGPEA_N@Z`
- size: `280`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013e68`

## callees

- `0x18000a5b4`
- `0x180013dc8`
- `0x180013ec4`
- `0x180015ca4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013fc9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013f7b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013f7b`

## string_xrefs

- `0x180013f07`: `onecore\ds\security\ngc\utils\common\lib\devicelockutils.cpp`
- `0x180013f8f`: `onecore\ds\security\ngc\utils\common\lib\devicelockutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::DeviceLockIsValueSet(NgcUtils *this, unsigned __int16 *a2, bool *a3)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  HLOCAL v7; // rbx
  unsigned int ValueW; // eax
  unsigned int v9; // edi
  int pdwType; // [rsp+20h] [rbp-28h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  NgcUtils *pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF

  pvData = this;
  *(_BYTE *)a2 = 0;
  hMem = 0;
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcLogonUi",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\NgcPin",
                                        0,
                                        &hMem);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\devicelockutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      pdwType);
    if ( hMem )
      LocalFree(hMem);
    return v5;
  }
  v7 = hMem;
  LODWORD(pvData) = 0;
  pcbData = 4;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)hMem, L"DeviceLockEnforcementPending", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW != 2 )
  {
    if ( ValueW )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x27,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\devicelockutils.cpp",
             (const char *)ValueW,
             pdwTypea);
      if ( v7 )
        LocalFree(v7);
      return v9;
    }
    *(_BYTE *)a2 = (_DWORD)pvData != 0;
  }
  if ( v7 )
    LocalFree(v7);
  return 0;
}

```

## disassembly

```asm
0x180013ec4  mov     rax, rsp
0x180013ec7  mov     [rax+20h], rbx
0x180013ecb  mov     [rax+8], rcx
0x180013ecf  push    rdi
0x180013ed0  sub     rsp, 40h
0x180013ed4  mov     rdi, rdx
0x180013ed7  mov     byte ptr [rdx], 0
0x180013eda  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180013ee1  mov     qword ptr [rax+18h], 0
0x180013ee9  lea     r9, [rax+18h]; unsigned __int16 *
0x180013eed  xor     r8d, r8d; unsigned __int16 *
0x180013ef0  lea     rcx, aNgclogonui; "NgcLogonUi"
0x180013ef7  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180013efc  mov     ebx, eax
0x180013efe  test    eax, eax
0x180013f00  jns     short loc_180013F32
0x180013f02  mov     rcx, [rsp+48h]; this
0x180013f07  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013f0e  mov     r9d, eax; char *
0x180013f11  mov     edx, 1Ah; void *
0x180013f16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f1b  mov     rcx, [rsp+48h+hMem]; hMem
0x180013f20  test    rcx, rcx
0x180013f23  jz      short loc_180013F2B
0x180013f25  call    cs:__imp_LocalFree
0x180013f2b  mov     eax, ebx
0x180013f2d  jmp     loc_180013FD1
0x180013f32  mov     rbx, [rsp+48h+hMem]
0x180013f37  lea     rax, [rsp+48h+arg_8]
0x180013f3c  mov     [rsp+48h+pcbData], rax; pcbData
0x180013f41  lea     r8, Value; "DeviceLockEnforcementPending"
0x180013f48  lea     rax, [rsp+48h+arg_0]
0x180013f4d  mov     dword ptr [rsp+48h+arg_0], 0
0x180013f55  mov     [rsp+48h+pvData], rax; pvData
0x180013f5a  mov     r9d, 10h; dwFlags
0x180013f60  mov     rdx, rbx; lpSubKey
0x180013f63  mov     [rsp+48h+pdwType], 0; unsigned int
0x180013f6c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180013f73  mov     [rsp+48h+arg_8], 4
0x180013f7b  call    cs:__imp_RegGetValueW
0x180013f81  cmp     eax, 2
0x180013f84  jz      short loc_180013FC1
0x180013f86  test    eax, eax
0x180013f88  jz      short loc_180013FB7
0x180013f8a  mov     rcx, [rsp+48h]; this
0x180013f8f  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013f96  mov     r9d, eax; char *
0x180013f99  mov     edx, 27h ; '''; void *
0x180013f9e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013fa3  mov     edi, eax
0x180013fa5  test    rbx, rbx
0x180013fa8  jz      short loc_180013FB3
0x180013faa  mov     rcx, rbx; hMem
0x180013fad  call    cs:__imp_LocalFree
0x180013fb3  mov     eax, edi
0x180013fb5  jmp     short loc_180013FD1
0x180013fb7  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013fbc  setnz   al
0x180013fbf  mov     [rdi], al
0x180013fc1  test    rbx, rbx
0x180013fc4  jz      short loc_180013FCF
0x180013fc6  mov     rcx, rbx; hMem
0x180013fc9  call    cs:__imp_LocalFree
0x180013fcf  xor     eax, eax
0x180013fd1  mov     rbx, [rsp+48h+arg_18]
0x180013fd6  add     rsp, 40h
0x180013fda  pop     rdi
0x180013fdb  retn
```
