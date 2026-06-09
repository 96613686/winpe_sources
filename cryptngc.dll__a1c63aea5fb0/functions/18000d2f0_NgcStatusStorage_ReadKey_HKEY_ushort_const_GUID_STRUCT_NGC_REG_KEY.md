# NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)

- ea: `0x18000d2f0`
- end: `0x18000d523`
- name: `?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z`
- size: `563`
- prototype: `static unsigned int(HKEY, const unsigned __int16 *, struct _GUID *__struct_ptr, struct STRUCT_NGC_REG_KEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009050`

## callees

- `0x18000c1b0`
- `0x18000ced0`
- `0x18000d2f0`
- `0x18000d530`
- `0x180026f88`
- `0x180027448`
- `0x18002cd24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d341`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d4c7`

## string_xrefs

- `0x18000d3a4`: `RegReadDwordValue`
- `0x18000d43a`: `RegReadStringValue`
- `0x18000d361`: `NgcStatusStorage::ReadKey`
- `0x18000d3ae`: `NgcStatusStorage::ReadKey`
- `0x18000d350`: `RegOpenKeyExW`
- `0x18000d36b`: `%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::ReadKey(
        HKEY a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct STRUCT_NGC_REG_KEY *a4)
{
  unsigned __int16 **v4; // r14
  unsigned __int16 **v5; // r15
  unsigned __int16 **v6; // r12
  unsigned __int16 **v7; // r13
  struct STRUCT_NGC_REG_KEY *v8; // rdi
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned int DwordValue; // eax
  const wchar_t *v14; // r8
  __int64 v15; // rax
  SIZE_T dwBytes; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytesa; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytesb; // [rsp+20h] [rbp-58h]
  SIZE_T dwBytesc; // [rsp+20h] [rbp-58h]
  unsigned int v21; // [rsp+28h] [rbp-50h]
  unsigned int v22; // [rsp+28h] [rbp-50h]
  unsigned int v23; // [rsp+28h] [rbp-50h]
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF

  v4 = (unsigned __int16 **)((char *)a4 + 16);
  v5 = (unsigned __int16 **)((char *)a4 + 40);
  hKey = 0;
  v6 = (unsigned __int16 **)((char *)a4 + 48);
  *((_QWORD *)a4 + 2) = 0;
  v7 = (unsigned __int16 **)((char *)a4 + 56);
  *((_QWORD *)a4 + 5) = 0;
  *((_QWORD *)a4 + 6) = 0;
  v8 = a4;
  *((_QWORD *)a4 + 7) = 0;
  v11 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v12 = v11;
  if ( v11 )
  {
    Logger::WriteRegistryFailureEvent(v11, L"RegOpenKeyExW", a2);
    Logger::TraceInformation(
      L"%s: Cannot open NGC key registry. Key name: %s. Error code: 0x%08x.",
      L"NgcStatusStorage::ReadKey",
      a2,
      v12);
    goto LABEL_14;
  }
  DwordValue = RegReadDwordValue(hKey, 0, L"AttestationLevel", a2, (unsigned int *)v8 + 6, v21);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadDwordValue(hKey, 0, L"AikCertStatus", a2, (unsigned int *)v8 + 7, v22),
        (v12 = DwordValue) != 0)
    || (DwordValue = RegReadDwordValue(hKey, 0, L"NgcKeyStatus", a2, (unsigned int *)v8 + 8, v23),
        (v12 = DwordValue) != 0) )
  {
    v14 = L"RegReadDwordValue";
LABEL_5:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"NgcStatusStorage::ReadKey", v14, DwordValue);
    goto LABEL_14;
  }
  DwordValue = RegReadStringValue(hKey, 0, L"NgcKeyName", a2, dwBytes, v4);
  v12 = DwordValue;
  if ( DwordValue
    || (DwordValue = RegReadStringValue(hKey, 0, L"IdpDomain", a2, dwBytesa, v5), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"TenantDomain", a2, dwBytesb, v6), (v12 = DwordValue) != 0)
    || (DwordValue = RegReadStringValue(hKey, 0, L"UserId", a2, dwBytesc, v7), (v12 = DwordValue) != 0) )
  {
    v14 = L"RegReadStringValue";
    goto LABEL_5;
  }
  *(struct _GUID *)v8 = *a3;
LABEL_14:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v12 )
  {
    SafeFree(*v4);
    SafeFree(*v5);
    SafeFree(*v6);
    SafeFree(*v7);
    v15 = 64;
    do
    {
      *(_BYTE *)v8 = 0;
      v8 = (struct STRUCT_NGC_REG_KEY *)((char *)v8 + 1);
      --v15;
    }
    while ( v15 );
  }
  return v12;
}

```

## disassembly

```asm
0x18000d2f0  mov     r11, rsp
0x18000d2f3  push    rbx
0x18000d2f4  push    rbp
0x18000d2f5  push    rsi
0x18000d2f6  push    rdi
0x18000d2f7  push    r12
0x18000d2f9  push    r13
0x18000d2fb  push    r14
0x18000d2fd  push    r15
0x18000d2ff  sub     rsp, 38h
0x18000d303  xor     eax, eax
0x18000d305  lea     r14, [r9+10h]
0x18000d309  lea     r15, [r9+28h]
0x18000d30d  mov     [r11+20h], rax
0x18000d311  lea     r12, [r9+30h]
0x18000d315  mov     [r14], rax
0x18000d318  lea     r13, [r9+38h]
0x18000d31c  mov     [r15], rax
0x18000d31f  mov     [r12], rax
0x18000d323  mov     rdi, r9
0x18000d326  mov     [r13+0], rax
0x18000d32a  mov     rbp, r8
0x18000d32d  lea     rax, [r11+20h]
0x18000d331  mov     r9d, 20019h; samDesired
0x18000d337  xor     r8d, r8d; ulOptions
0x18000d33a  mov     [r11-58h], rax
0x18000d33e  mov     rsi, rdx
0x18000d341  call    cs:__imp_RegOpenKeyExW
0x18000d347  mov     ebx, eax
0x18000d349  test    eax, eax
0x18000d34b  jz      short loc_18000D37C
0x18000d34d  mov     r8, rsi; unsigned __int16 *
0x18000d350  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000d357  mov     ecx, eax; unsigned int
0x18000d359  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18000d35e  mov     r9d, ebx
0x18000d361  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x18000d368  mov     r8, rsi
0x18000d36b  lea     rcx, aSCannotOpenNgc; "%s: Cannot open NGC key registry. Key n"...
0x18000d372  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18000d377  jmp     loc_18000D4BA
0x18000d37c  mov     rcx, [rsp+78h+hKey]; HKEY
0x18000d384  lea     rax, [rdi+18h]
0x18000d388  mov     r9, rsi; unsigned __int16 *
0x18000d38b  mov     [rsp+78h+dwBytes], rax; unsigned int *
0x18000d390  lea     r8, aAttestationlev; "AttestationLevel"
0x18000d397  xor     edx, edx; unsigned __int16 *
0x18000d399  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18000d39e  mov     ebx, eax
0x18000d3a0  test    eax, eax
0x18000d3a2  jz      short loc_18000D3C6
0x18000d3a4  lea     r8, aRegreaddwordva; "RegReadDwordValue"
0x18000d3ab  mov     r9d, eax
0x18000d3ae  lea     rdx, aNgcstatusstora_0; "NgcStatusStorage::ReadKey"
0x18000d3b5  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000d3bc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d3c1  jmp     loc_18000D4BA
0x18000d3c6  mov     rcx, [rsp+78h+hKey]; HKEY
0x18000d3ce  lea     rax, [rdi+1Ch]
0x18000d3d2  mov     r9, rsi; unsigned __int16 *
0x18000d3d5  mov     [rsp+78h+dwBytes], rax; unsigned int *
0x18000d3da  lea     r8, aAikcertstatus; "AikCertStatus"
0x18000d3e1  xor     edx, edx; unsigned __int16 *
0x18000d3e3  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18000d3e8  mov     ebx, eax
0x18000d3ea  test    eax, eax
0x18000d3ec  jnz     short loc_18000D3A4
0x18000d3ee  mov     rcx, [rsp+78h+hKey]; HKEY
0x18000d3f6  lea     rax, [rdi+20h]
0x18000d3fa  mov     r9, rsi; unsigned __int16 *
0x18000d3fd  mov     [rsp+78h+dwBytes], rax; dwBytes
0x18000d402  lea     r8, aNgckeystatus; "NgcKeyStatus"
0x18000d409  xor     edx, edx; unsigned __int16 *
0x18000d40b  call    ?RegReadDwordValue@@YAKPEAUHKEY__@@PEBG11PEAKK@Z; RegReadDwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong *,ulong)
0x18000d410  mov     ebx, eax
0x18000d412  test    eax, eax
0x18000d414  jnz     short loc_18000D3A4
0x18000d416  mov     rcx, [rsp+78h+hKey]; hkey
0x18000d41e  lea     r8, aNgckeyname; "NgcKeyName"
0x18000d425  mov     r9, rsi; unsigned __int16 *
0x18000d428  mov     qword ptr [rsp+78h+var_50], r14; unsigned __int16 **
0x18000d42d  xor     edx, edx; lpSubKey
0x18000d42f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18000d434  mov     ebx, eax
0x18000d436  test    eax, eax
0x18000d438  jz      short loc_18000D446
0x18000d43a  lea     r8, aRegreadstringv; "RegReadStringValue"
0x18000d441  jmp     loc_18000D3AB
0x18000d446  mov     rcx, [rsp+78h+hKey]; hkey
0x18000d44e  lea     r8, aIdpdomain; "IdpDomain"
0x18000d455  mov     r9, rsi; unsigned __int16 *
0x18000d458  mov     qword ptr [rsp+78h+var_50], r15; unsigned __int16 **
0x18000d45d  xor     edx, edx; lpSubKey
0x18000d45f  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18000d464  mov     ebx, eax
0x18000d466  test    eax, eax
0x18000d468  jnz     short loc_18000D43A
0x18000d46a  mov     rcx, [rsp+78h+hKey]; hkey
0x18000d472  lea     r8, aTenantdomain; "TenantDomain"
0x18000d479  mov     r9, rsi; unsigned __int16 *
0x18000d47c  mov     qword ptr [rsp+78h+var_50], r12; unsigned __int16 **
0x18000d481  xor     edx, edx; lpSubKey
0x18000d483  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18000d488  mov     ebx, eax
0x18000d48a  test    eax, eax
0x18000d48c  jnz     short loc_18000D43A
0x18000d48e  mov     rcx, [rsp+78h+hKey]; hkey
0x18000d496  lea     r8, aUserid; "UserId"
0x18000d49d  mov     r9, rsi; unsigned __int16 *
0x18000d4a0  mov     qword ptr [rsp+78h+var_50], r13; unsigned __int16 **
0x18000d4a5  xor     edx, edx; lpSubKey
0x18000d4a7  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18000d4ac  mov     ebx, eax
0x18000d4ae  test    eax, eax
0x18000d4b0  jnz     short loc_18000D43A
0x18000d4b2  movaps  xmm0, xmmword ptr [rbp+0]
0x18000d4b6  movdqu  xmmword ptr [rdi], xmm0
0x18000d4ba  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d4c2  test    rcx, rcx
0x18000d4c5  jz      short loc_18000D4D9
0x18000d4c7  call    cs:__imp_RegCloseKey
0x18000d4cd  mov     [rsp+78h+hKey], 0
0x18000d4d9  test    ebx, ebx
0x18000d4db  jz      short loc_18000D510
0x18000d4dd  mov     rcx, [r14]; lpMem
0x18000d4e0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000d4e5  mov     rcx, [r15]; lpMem
0x18000d4e8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000d4ed  mov     rcx, [r12]; lpMem
0x18000d4f1  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000d4f6  mov     rcx, [r13+0]; lpMem
0x18000d4fa  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000d4ff  mov     eax, 40h ; '@'
0x18000d504  mov     byte ptr [rdi], 0
0x18000d507  inc     rdi
0x18000d50a  sub     rax, 1
0x18000d50e  jnz     short loc_18000D504
0x18000d510  mov     eax, ebx
0x18000d512  add     rsp, 38h
0x18000d516  pop     r15
0x18000d518  pop     r14
0x18000d51a  pop     r13
0x18000d51c  pop     r12
0x18000d51e  pop     rdi
0x18000d51f  pop     rsi
0x18000d520  pop     rbp
0x18000d521  pop     rbx
0x18000d522  retn
```
