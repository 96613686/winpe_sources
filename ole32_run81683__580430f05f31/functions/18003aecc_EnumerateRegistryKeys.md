# EnumerateRegistryKeys

- ea: `0x18003aecc`
- end: `0x18003aff6`
- name: `EnumerateRegistryKeys`
- size: `298`
- prototype: `HRESULT __fastcall(HREG hkey, unsigned int index, wchar_t **pwsz)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016b10`

## callees

- `0x180017894`
- `0x18003aecc`
- `0x1800c4651`

## import_xrefs

- `ntdll!ZwEnumerateKey` at `0x18003af30`
- `ntdll!ZwEnumerateKey` at `0x18003af30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003af90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003afd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003afd7`

## pseudocode

```c
__int64 __fastcall EnumerateRegistryKeys(HREG hkey, ULONG index, wchar_t **pwsz)
{
  unsigned int v3; // esi
  _DWORD *v5; // rdi
  ULONG Length; // r14d
  NTSTATUS v9; // eax
  int v10; // ebp
  unsigned int v11; // eax
  SIZE_T v12; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  unsigned int cbResult; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  *pwsz = 0;
  v5 = 0;
  Length = 260;
  while ( !v3 )
  {
    v5 = CoTaskMemAlloc(Length);
    if ( v5 )
    {
      cbResult = 0;
      v9 = ZwEnumerateKey(hkey.h, index, KeyBasicInformation, v5, Length, &cbResult);
      v10 = v9;
      switch ( v9 )
      {
        case -2147483643:
        case -1073741789:
          CoTaskMemFree(v5);
          Length *= 2;
          break;
        case -2147483622:
          goto LABEL_17;
        case 0:
          v11 = v5[3];
          v12 = v11 + 2;
          if ( (unsigned int)v12 < v11 )
          {
            v3 = -2147024362;
          }
          else
          {
            v13 = (wchar_t *)CoTaskMemAlloc(v12);
            v14 = v13;
            if ( v13 )
            {
              v3 = 0;
              memcpy_0(v13, v5 + 4, (unsigned int)v5[3]);
              v14[(unsigned __int64)(unsigned int)v5[3] >> 1] = 0;
              *pwsz = v14;
            }
            else
            {
              v3 = -2147024882;
            }
          }
          goto LABEL_17;
        default:
          CoTaskMemFree(v5);
          v5 = 0;
          v3 = HrNt(v10);
          break;
      }
    }
    else
    {
      v3 = -2147024882;
    }
  }
  if ( !v5 )
    return v3;
LABEL_17:
  CoTaskMemFree(v5);
  return v3;
}

```

## disassembly

```asm
0x18003aecc  mov     [rsp+arg_0], rbx
0x18003aed1  mov     [rsp+arg_8], rbp
0x18003aed6  push    rsi
0x18003aed7  push    rdi
0x18003aed8  push    r12
0x18003aeda  push    r14
0x18003aedc  push    r15
0x18003aede  sub     rsp, 30h
0x18003aee2  xor     esi, esi
0x18003aee4  mov     r15, pwsz
0x18003aee7  mov     [pwsz], rsi
0x18003aeea  xor     edi, edi
0x18003aeec  mov     r12d, index
0x18003aeef  mov     rbx, hkey
0x18003aef2  mov     r14d, 104h
0x18003aef8  test    esi, esi
0x18003aefa  jnz     loc_18003AFCF
0x18003af00  mov     ecx, r14d; cb
0x18003af03  call    cs:__imp_CoTaskMemAlloc
0x18003af09  mov     rdi, rax
0x18003af0c  test    rax, rax
0x18003af0f  jz      short loc_18003AF7C
0x18003af11  lea     rax, [rsp+58h+cbResult]
0x18003af16  mov     [rsp+58h+cbResult], esi
0x18003af1a  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18003af1f  mov     r9, rdi; KeyInformation
0x18003af22  xor     r8d, r8d; KeyInformationClass
0x18003af25  mov     [rsp+58h+Length], r14d; Length
0x18003af2a  mov     index, r12d; Index
0x18003af2d  mov     hkey, rbx; KeyHandle
0x18003af30  call    cs:__imp_ZwEnumerateKey
0x18003af36  mov     ebp, eax
0x18003af38  cmp     eax, 80000005h
0x18003af3d  jz      short loc_18003AF6B
0x18003af3f  cmp     eax, 0C0000023h
0x18003af44  jz      short loc_18003AF6B
0x18003af46  cmp     eax, 8000001Ah
0x18003af4b  jz      loc_18003AFD4
0x18003af51  test    eax, eax
0x18003af53  jz      short loc_18003AF86
0x18003af55  mov     hkey, rdi; pv
0x18003af58  call    cs:__imp_CoTaskMemFree
0x18003af5e  mov     ecx, ebp; status
0x18003af60  xor     edi, edi
0x18003af62  call    HrNt
0x18003af67  mov     esi, eax
0x18003af69  jmp     short loc_18003AEF8
0x18003af6b  mov     hkey, rdi; pv
0x18003af6e  call    cs:__imp_CoTaskMemFree
0x18003af74  add     r14d, r14d
0x18003af77  jmp     loc_18003AEF8
0x18003af7c  mov     esi, 8007000Eh
0x18003af81  jmp     loc_18003AEF8
0x18003af86  mov     eax, [rdi+0Ch]
0x18003af89  lea     ecx, [rax+2]; cb
0x18003af8c  cmp     ecx, eax
0x18003af8e  jb      short loc_18003AFC8
0x18003af90  call    cs:__imp_CoTaskMemAlloc
0x18003af96  mov     rbx, rax
0x18003af99  test    rax, rax
0x18003af9c  jz      short loc_18003AFC1
0x18003af9e  mov     r8d, [rdi+0Ch]; Size
0x18003afa2  lea     rdx, [rdi+10h]; Src
0x18003afa6  mov     hkey, rax; void *
0x18003afa9  xor     esi, esi
0x18003afab  call    memcpy_0
0x18003afb0  mov     index, [rdi+0Ch]
0x18003afb3  shr     rdx, 1
0x18003afb6  xor     ecx, ecx
0x18003afb8  mov     [rbx+rdx*2], cx
0x18003afbc  mov     [r15], rbx
0x18003afbf  jmp     short loc_18003AFD4
0x18003afc1  mov     esi, 8007000Eh
0x18003afc6  jmp     short loc_18003AFD4
0x18003afc8  mov     esi, 80070216h
0x18003afcd  jmp     short loc_18003AFD4
0x18003afcf  test    rdi, rdi
0x18003afd2  jz      short loc_18003AFDD
0x18003afd4  mov     hkey, rdi; pv
0x18003afd7  call    cs:__imp_CoTaskMemFree
0x18003afdd  mov     rbx, [rsp+58h+arg_0]
0x18003afe2  mov     eax, esi
0x18003afe4  mov     rbp, [rsp+58h+arg_8]
0x18003afe9  add     rsp, 30h
0x18003afed  pop     r15
0x18003afef  pop     r14
0x18003aff1  pop     r12
0x18003aff3  pop     rdi
0x18003aff4  pop     rsi
0x18003aff5  retn
```
