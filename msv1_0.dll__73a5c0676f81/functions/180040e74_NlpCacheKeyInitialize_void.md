# NlpCacheKeyInitialize(void)

- ea: `0x180040e74`
- end: `0x180040fe4`
- name: `?NlpCacheKeyInitialize@@YAJXZ`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800425d0`

## callees

- `0x18001a258`
- `0x180040e74`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040fd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040fd9`
- `ntdll!RtlInitUnicodeString` at `0x180040e99`
- `ntdll!RtlInitUnicodeString` at `0x180040e99`
- `LSASRV!LsarSetSecret` at `0x180040f26`
- `LSASRV!LsarSetSecret` at `0x180040f26`
- `LSASRV!LsarCreateSecret` at `0x180040ede`
- `LSASRV!LsarCreateSecret` at `0x180040ede`
- `LSASRV!LsarClose` at `0x180040f32`
- `LSASRV!LsarClose` at `0x180040f32`
- `LSASRV!LsarQuerySecret` at `0x180040f6a`
- `LSASRV!LsarQuerySecret` at `0x180040f6a`
- `LSASRV!LsarOpenSecret` at `0x180040eb4`
- `LSASRV!LsarOpenSecret` at `0x180040eb4`

## pseudocode

```c
__int64 NlpCacheKeyInitialize(void)
{
  __int64 result; // rax
  int RandomBits; // ebx
  HLOCAL v2; // rcx
  _OWORD *v3; // rax
  __int64 v4; // rax
  _BYTE *v5; // rdx
  __int128 v6; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  __int64 v8; // [rsp+70h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+28h] BYREF
  __int64 v10; // [rsp+80h] [rbp+30h] BYREF

  v8 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"NL$KM");
  result = LsarOpenSecret(NtLmGlobalPolicyHandle, &DestinationString, 3, &v8);
  if ( (int)result >= 0 )
  {
    v10 = 0;
    hMem = 0;
    RandomBits = LsarQuerySecret(v8, &hMem, &v10, 0, 0);
    if ( RandomBits < 0 )
    {
LABEL_6:
      LsarClose(&v8);
      return (unsigned int)RandomBits;
    }
    v2 = hMem;
    if ( hMem )
    {
      if ( *(_DWORD *)hMem == 64 )
      {
        v3 = (_OWORD *)*((_QWORD *)hMem + 1);
        *(_OWORD *)&NlpCacheEncryptionKey = *v3;
        xmmword_1800870A0 = v3[1];
        xmmword_1800870B0 = v3[2];
        xmmword_1800870C0 = v3[3];
      }
      else
      {
        RandomBits = -1073741481;
      }
      v4 = *(unsigned int *)hMem;
      v5 = (_BYTE *)*((_QWORD *)hMem + 1);
      if ( *(_DWORD *)hMem )
      {
        do
        {
          *v5++ = 0;
          --v4;
        }
        while ( v4 );
        v2 = hMem;
      }
      LocalFree(v2);
      goto LABEL_6;
    }
LABEL_4:
    v6 = 0;
    RandomBits = SspGenerateRandomBits(&NlpCacheEncryptionKey, 64);
    if ( RandomBits >= 0 )
    {
      *(_QWORD *)&v6 = 0x4000000040LL;
      *((_QWORD *)&v6 + 1) = &NlpCacheEncryptionKey;
      RandomBits = LsarSetSecret(v8, &v6, 0);
    }
    goto LABEL_6;
  }
  if ( (_DWORD)result == -1073741772 )
  {
    result = LsarCreateSecret(NtLmGlobalPolicyHandle, &DestinationString, 1, &v8);
    if ( (int)result >= 0 )
      goto LABEL_4;
  }
  return result;
}

```

## disassembly

```asm
0x180040e74  push    rbp
0x180040e76  push    rbx
0x180040e77  push    rsi
0x180040e78  mov     rbp, rsp
0x180040e7b  sub     rsp, 50h
0x180040e7f  xorps   xmm0, xmm0
0x180040e82  mov     [rbp+arg_0], 0
0x180040e8a  lea     rdx, aNlKm; "NL$KM"
0x180040e91  lea     rcx, [rbp+DestinationString]; DestinationString
0x180040e95  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180040e99  call    cs:__imp_RtlInitUnicodeString
0x180040e9f  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180040ea6  lea     r9, [rbp+arg_0]
0x180040eaa  mov     r8d, 3
0x180040eb0  lea     rdx, [rbp+DestinationString]
0x180040eb4  call    cs:__imp_LsarOpenSecret
0x180040eba  test    eax, eax
0x180040ebc  jns     loc_180040F42
0x180040ec2  cmp     eax, 0C0000034h
0x180040ec7  jnz     short loc_180040F3A
0x180040ec9  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180040ed0  lea     r9, [rbp+arg_0]
0x180040ed4  mov     r8d, 1
0x180040eda  lea     rdx, [rbp+DestinationString]
0x180040ede  call    cs:__imp_LsarCreateSecret
0x180040ee4  test    eax, eax
0x180040ee6  js      short loc_180040F3A
0x180040ee8  xorps   xmm0, xmm0
0x180040eeb  lea     rsi, ?NlpCacheEncryptionKey@@3PADA; char near * NlpCacheEncryptionKey
0x180040ef2  mov     rcx, rsi
0x180040ef5  mov     edx, 40h ; '@'
0x180040efa  movups  [rbp+var_20], xmm0
0x180040efe  call    SspGenerateRandomBits
0x180040f03  mov     ebx, eax
0x180040f05  test    eax, eax
0x180040f07  js      short loc_180040F2E
0x180040f09  mov     rcx, [rbp+arg_0]
0x180040f0d  lea     rdx, [rbp+var_20]
0x180040f11  xor     r8d, r8d
0x180040f14  mov     dword ptr [rbp+var_20], 40h ; '@'
0x180040f1b  mov     dword ptr [rbp+var_20+4], 40h ; '@'
0x180040f22  mov     qword ptr [rbp+var_20+8], rsi
0x180040f26  call    cs:__imp_LsarSetSecret
0x180040f2c  mov     ebx, eax
0x180040f2e  lea     rcx, [rbp+arg_0]
0x180040f32  call    cs:__imp_LsarClose
0x180040f38  mov     eax, ebx
0x180040f3a  add     rsp, 50h
0x180040f3e  pop     rsi
0x180040f3f  pop     rbx
0x180040f40  pop     rbp
0x180040f41  retn
0x180040f42  mov     rcx, [rbp+arg_0]
0x180040f46  lea     r8, [rbp+arg_10]
0x180040f4a  xor     r9d, r9d
0x180040f4d  mov     [rbp+arg_10], 0
0x180040f55  lea     rdx, [rbp+hMem]
0x180040f59  mov     [rbp+hMem], 0
0x180040f61  mov     [rsp+50h+var_30], 0
0x180040f6a  call    cs:__imp_LsarQuerySecret
0x180040f70  mov     ebx, eax
0x180040f72  test    eax, eax
0x180040f74  js      short loc_180040F2E
0x180040f76  mov     rcx, [rbp+hMem]
0x180040f7a  test    rcx, rcx
0x180040f7d  jz      loc_180040EE8
0x180040f83  cmp     dword ptr [rcx], 40h ; '@'
0x180040f86  jz      short loc_180040F8F
0x180040f88  mov     ebx, 0C0000157h
0x180040f8d  jmp     short loc_180040FBE
0x180040f8f  mov     rax, [rcx+8]
0x180040f93  movups  xmm0, xmmword ptr [rax]
0x180040f96  movaps  cs:?NlpCacheEncryptionKey@@3PADA, xmm0; char near * NlpCacheEncryptionKey
0x180040f9d  movups  xmm1, xmmword ptr [rax+10h]
0x180040fa1  movaps  cs:xmmword_1800870A0, xmm1
0x180040fa8  movups  xmm0, xmmword ptr [rax+20h]
0x180040fac  movaps  cs:xmmword_1800870B0, xmm0
0x180040fb3  movups  xmm1, xmmword ptr [rax+30h]
0x180040fb7  movaps  cs:xmmword_1800870C0, xmm1
0x180040fbe  mov     eax, [rcx]
0x180040fc0  mov     rdx, [rcx+8]
0x180040fc4  test    rax, rax
0x180040fc7  jz      short loc_180040FD9
0x180040fc9  mov     byte ptr [rdx], 0
0x180040fcc  inc     rdx
0x180040fcf  sub     rax, 1
0x180040fd3  jnz     short loc_180040FC9
0x180040fd5  mov     rcx, [rbp+hMem]; hMem
0x180040fd9  call    cs:__imp_LocalFree
0x180040fdf  jmp     loc_180040F2E
```
