# GetRegistryBinaryBlob(HKEY__ *,ushort const *,uchar * *,ulong *)

- ea: `0x1800acabc`
- end: `0x1800accd9`
- name: `?GetRegistryBinaryBlob@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z`
- size: `541`
- prototype: `__int64 __fastcall(HKEY hkey, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800abc38`

## callees

- `0x1800407cc`
- `0x1800417d0`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800acabc`
- `0x1800dc9e0`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acb8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acc36`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acb8e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800acc36`

## string_xrefs

- `0x1800acb01`: `AppSid`
- `0x1800acb26`: `AppSid`
- `0x1800acc1c`: `AppSid`

## pseudocode

```c
__int64 __fastcall GetRegistryBinaryBlob(HKEY hkey, const unsigned __int16 *a2, unsigned __int8 **a3, unsigned int *a4)
{
  void *v4; // rbx
  unsigned int v8; // edi
  __int64 v9; // r9
  LSTATUS ValueW; // eax
  __int64 v11; // rcx
  int v12; // edi
  size_t v13; // r15
  void *Heap; // rax
  void *pvData; // rbp
  LSTATUS v16; // eax
  DWORD v17; // eax
  void *v19; // [rsp+48h] [rbp-50h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-48h] BYREF

  v4 = 0;
  v19 = 0;
  pcbData = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qq(1035, 18, (unsigned int)WPP_138624eb8f853fa9b59f3df64d0a99bc_Traceguids, (_DWORD)hkey, (__int64)L"AppSid");
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !a3 )
  {
    v8 = -2147024809;
    v9 = 2147942487LL;
    goto LABEL_25;
  }
  if ( !a4 )
  {
    v8 = -2147024809;
    v9 = 2147942487LL;
    goto LABEL_25;
  }
  ValueW = RegGetValueW(hkey, 0, L"AppSid", 3u, 0, 0, &pcbData);
  v12 = ValueW;
  if ( ValueW > 0 )
    v9 = (unsigned __int16)ValueW | 0x80070000;
  else
    v9 = (unsigned int)ValueW;
  if ( (int)v9 >= 0 )
  {
    v13 = pcbData;
    Heap = (void *)WxAllocateHeapEx(v11, pcbData);
    pvData = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, v13);
      v4 = pvData;
      v19 = pvData;
      v16 = RegGetValueW(hkey, 0, L"AppSid", 3u, 0, pvData, &pcbData);
      v9 = (unsigned int)v16;
      if ( v16 < 0 )
      {
        v8 = v16;
        goto LABEL_25;
      }
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      else
        v9 = (unsigned int)v12;
      if ( (int)v9 >= 0 )
      {
        v17 = pcbData;
        *a3 = (unsigned __int8 *)pvData;
        v4 = 0;
        v19 = 0;
        *a4 = v17;
      }
    }
    else
    {
      v9 = 2147942414LL;
    }
  }
  v8 = v9;
LABEL_25:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 19, WPP_138624eb8f853fa9b59f3df64d0a99bc_Traceguids, v9);
  if ( v4 )
    WxFreeHeapEx(&v19);
  return v8;
}

```

## disassembly

```asm
0x1800acabc  push    rbx
0x1800acabe  push    rbp
0x1800acabf  push    rsi
0x1800acac0  push    rdi
0x1800acac1  push    r12
0x1800acac3  push    r14
0x1800acac5  push    r15
0x1800acac7  sub     rsp, 60h
0x1800acacb  mov     rax, cs:__security_cookie
0x1800acad2  xor     rax, rsp
0x1800acad5  mov     [rsp+98h+var_40], rax
0x1800acada  xor     ebx, ebx
0x1800acadc  mov     [rsp+98h+var_54], 0
0x1800acae4  mov     [rsp+98h+var_50], rbx
0x1800acae9  mov     r14, r9
0x1800acaec  mov     rsi, r8
0x1800acaef  mov     [rsp+98h+var_48], 0
0x1800acaf7  mov     r12, rcx
0x1800acafa  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800acb01  lea     r8, aAppsid; "AppSid"
0x1800acb08  jz      short loc_1800ACB2D
0x1800acb0a  mov     [rsp+98h+pdwType], r8
0x1800acb0f  lea     edx, [rbx+12h]
0x1800acb12  lea     r8, WPP_138624eb8f853fa9b59f3df64d0a99bc_Traceguids
0x1800acb19  mov     ecx, 40Bh
0x1800acb1e  mov     r9, r12
0x1800acb21  call    WPP_SF_qq
0x1800acb26  lea     r8, aAppsid; "AppSid"
0x1800acb2d  test    rsi, rsi
0x1800acb30  jz      short loc_1800ACB35
0x1800acb32  mov     [rsi], rbx
0x1800acb35  test    r14, r14
0x1800acb38  jz      short loc_1800ACB3D
0x1800acb3a  mov     [r14], ebx
0x1800acb3d  test    rsi, rsi
0x1800acb40  jnz     short loc_1800ACB57
0x1800acb42  mov     edi, 80070057h
0x1800acb47  mov     [rsp+98h+var_54], 0E8h
0x1800acb4f  mov     r9d, edi
0x1800acb52  jmp     loc_1800ACC8C
0x1800acb57  test    r14, r14
0x1800acb5a  jnz     short loc_1800ACB71
0x1800acb5c  mov     edi, 80070057h
0x1800acb61  mov     [rsp+98h+var_54], 0E9h
0x1800acb69  mov     r9d, edi
0x1800acb6c  jmp     loc_1800ACC8C
0x1800acb71  xor     edx, edx; lpSubKey
0x1800acb73  lea     rax, [rsp+98h+var_48]
0x1800acb78  mov     [rsp+98h+pcbData], rax; pcbData
0x1800acb7d  mov     rcx, r12; hkey
0x1800acb80  mov     [rsp+98h+pvData], rbx; pvData
0x1800acb85  mov     [rsp+98h+pdwType], rbx; pdwType
0x1800acb8a  lea     r9d, [rdx+3]; dwFlags
0x1800acb8e  call    cs:__imp_RegGetValueW
0x1800acb95  nop     dword ptr [rax+rax+00h]
0x1800acb9a  mov     edi, eax
0x1800acb9c  test    eax, eax
0x1800acb9e  jg      short loc_1800ACBA5
0x1800acba0  mov     r9d, eax
0x1800acba3  jmp     short loc_1800ACBB0
0x1800acba5  movzx   r9d, di
0x1800acba9  or      r9d, 80070000h
0x1800acbb0  test    r9d, r9d
0x1800acbb3  jns     short loc_1800ACBC2
0x1800acbb5  mov     [rsp+98h+var_54], 0F3h
0x1800acbbd  jmp     loc_1800ACC89
0x1800acbc2  mov     eax, [rsp+98h+var_48]
0x1800acbc6  mov     edx, eax
0x1800acbc8  mov     [rsp+98h+var_54], ebx
0x1800acbcc  mov     r15d, eax
0x1800acbcf  call    WxAllocateHeapEx
0x1800acbd4  mov     rbp, rax
0x1800acbd7  test    rax, rax
0x1800acbda  jnz     short loc_1800ACBF7
0x1800acbdc  mov     [rsp+98h+var_54], 4Ch ; 'L'
0x1800acbe4  mov     r9d, 8007000Eh
0x1800acbea  mov     [rsp+98h+var_54], 0F5h
0x1800acbf2  jmp     loc_1800ACC89
0x1800acbf7  mov     r8, r15; Size
0x1800acbfa  xor     edx, edx; Val
0x1800acbfc  mov     rcx, rbp; void *
0x1800acbff  call    memset_0
0x1800acc04  mov     rbx, rbp
0x1800acc07  mov     [rsp+98h+var_50], rbx
0x1800acc0c  lea     rax, [rsp+98h+var_48]
0x1800acc11  mov     r9d, 3; dwFlags
0x1800acc17  mov     [rsp+98h+pcbData], rax; pcbData
0x1800acc1c  lea     r8, aAppsid; "AppSid"
0x1800acc23  mov     [rsp+98h+pvData], rbx; pvData
0x1800acc28  xor     edx, edx; lpSubKey
0x1800acc2a  mov     rcx, r12; hkey
0x1800acc2d  mov     [rsp+98h+pdwType], 0; pdwType
0x1800acc36  call    cs:__imp_RegGetValueW
0x1800acc3d  nop     dword ptr [rax+rax+00h]
0x1800acc42  mov     r9d, eax
0x1800acc45  test    eax, eax
0x1800acc47  jns     short loc_1800ACC55
0x1800acc49  mov     [rsp+98h+var_54], 0FDh
0x1800acc51  mov     edi, eax
0x1800acc53  jmp     short loc_1800ACC8C
0x1800acc55  test    edi, edi
0x1800acc57  jg      short loc_1800ACC5E
0x1800acc59  mov     r9d, edi
0x1800acc5c  jmp     short loc_1800ACC69
0x1800acc5e  movzx   r9d, di
0x1800acc62  or      r9d, 80070000h
0x1800acc69  test    r9d, r9d
0x1800acc6c  jns     short loc_1800ACC78
0x1800acc6e  mov     [rsp+98h+var_54], 0FEh
0x1800acc76  jmp     short loc_1800ACC89
0x1800acc78  mov     eax, [rsp+98h+var_48]
0x1800acc7c  mov     [rsi], rbx
0x1800acc7f  xor     ebx, ebx
0x1800acc81  mov     [rsp+98h+var_50], rbx
0x1800acc86  mov     [r14], eax
0x1800acc89  mov     edi, r9d
0x1800acc8c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800acc93  jz      short loc_1800ACCAB
0x1800acc95  mov     edx, 13h
0x1800acc9a  lea     r8, WPP_138624eb8f853fa9b59f3df64d0a99bc_Traceguids
0x1800acca1  mov     ecx, 40Bh
0x1800acca6  call    WPP_SF_d
0x1800accab  test    rbx, rbx
0x1800accae  jz      short loc_1800ACCBA
0x1800accb0  lea     rcx, [rsp+98h+var_50]
0x1800accb5  call    WxFreeHeapEx
0x1800accba  mov     eax, edi
0x1800accbc  mov     rcx, [rsp+98h+var_40]
0x1800accc1  xor     rcx, rsp; StackCookie
0x1800accc4  call    __security_check_cookie
0x1800accc9  add     rsp, 60h
0x1800acccd  pop     r15
0x1800acccf  pop     r14
0x1800accd1  pop     r12
0x1800accd3  pop     rdi
0x1800accd4  pop     rsi
0x1800accd5  pop     rbp
0x1800accd6  pop     rbx
0x1800accd7  retn
```
