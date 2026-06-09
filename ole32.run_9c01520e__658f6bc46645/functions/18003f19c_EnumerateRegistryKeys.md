# EnumerateRegistryKeys

- ea: `0x18003f19c`
- end: `0x18003f305`
- name: `EnumerateRegistryKeys`
- size: `361`
- prototype: `HRESULT __fastcall(HREG hkey, unsigned int index, wchar_t **pwsz)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013f54`

## callees

- `0x180020b10`
- `0x18003f19c`
- `0x1800ce967`

## import_xrefs

- `ntdll!ZwEnumerateKey` at `0x18003f216`
- `ntdll!ZwEnumerateKey` at `0x18003f216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f1de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f28f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f1de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003f28f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f2d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f2d9`

## pseudocode

```c
__int64 __fastcall EnumerateRegistryKeys(HREG hkey, ULONG index, wchar_t **pwsz)
{
  unsigned int v4; // esi
  _DWORD *v5; // rdi
  ULONG Length; // r14d
  NTSTATUS v9; // eax
  int v10; // ebp
  unsigned int v11; // eax
  SIZE_T v12; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  unsigned int cbResult; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  *pwsz = 0;
  v5 = 0;
  Length = 260;
  while ( !v4 )
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
            v4 = -2147024362;
          }
          else
          {
            v4 = 0;
            v13 = (wchar_t *)CoTaskMemAlloc(v12);
            v14 = v13;
            if ( v13 )
            {
              memcpy_0(v13, v5 + 4, (unsigned int)v5[3]);
              v14[(unsigned __int64)(unsigned int)v5[3] >> 1] = 0;
              *pwsz = v14;
            }
            else
            {
              v4 = -2147024882;
            }
          }
          goto LABEL_17;
        default:
          CoTaskMemFree(v5);
          v5 = 0;
          v4 = HrNt(v10);
          break;
      }
    }
    else
    {
      v4 = -2147024882;
    }
  }
  if ( !v5 )
    return v4;
LABEL_17:
  CoTaskMemFree(v5);
  return v4;
}

```

## disassembly

```asm
0x18003f19c  mov     [rsp+arg_0], rbx
0x18003f1a1  mov     [rsp+arg_8], rbp
0x18003f1a6  mov     [rsp+arg_18], rsi
0x18003f1ab  push    rdi
0x18003f1ac  push    r12
0x18003f1ae  push    r13
0x18003f1b0  push    r14
0x18003f1b2  push    r15
0x18003f1b4  sub     rsp, 30h
0x18003f1b8  xor     r13d, r13d
0x18003f1bb  mov     r15, pwsz
0x18003f1be  mov     esi, r13d
0x18003f1c1  mov     [pwsz], r13
0x18003f1c4  mov     edi, r13d
0x18003f1c7  mov     r12d, index
0x18003f1ca  mov     rbx, hkey
0x18003f1cd  mov     r14d, 104h
0x18003f1d3  test    esi, esi
0x18003f1d5  jnz     loc_18003F2D1
0x18003f1db  mov     ecx, r14d; cb
0x18003f1de  call    cs:__imp_CoTaskMemAlloc
0x18003f1e5  nop     dword ptr [rax+rax+00h]
0x18003f1ea  mov     rdi, rax
0x18003f1ed  test    rax, rax
0x18003f1f0  jz      loc_18003F278
0x18003f1f6  lea     rax, [rsp+58h+cbResult]
0x18003f1fb  mov     [rsp+58h+cbResult], r13d
0x18003f200  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18003f205  mov     r9, rdi; KeyInformation
0x18003f208  xor     r8d, r8d; KeyInformationClass
0x18003f20b  mov     [rsp+58h+Length], r14d; Length
0x18003f210  mov     index, r12d; Index
0x18003f213  mov     hkey, rbx; KeyHandle
0x18003f216  call    cs:__imp_ZwEnumerateKey
0x18003f21d  nop     dword ptr [rax+rax+00h]
0x18003f222  mov     ebp, eax
0x18003f224  cmp     eax, 80000005h
0x18003f229  jz      short loc_18003F261
0x18003f22b  cmp     eax, 0C0000023h
0x18003f230  jz      short loc_18003F261
0x18003f232  cmp     eax, 8000001Ah
0x18003f237  jz      loc_18003F2D6
0x18003f23d  test    eax, eax
0x18003f23f  jz      short loc_18003F282
0x18003f241  mov     hkey, rdi; pv
0x18003f244  call    cs:__imp_CoTaskMemFree
0x18003f24b  nop     dword ptr [rax+rax+00h]
0x18003f250  mov     ecx, ebp; status
0x18003f252  mov     rdi, r13
0x18003f255  call    HrNt
0x18003f25a  mov     esi, eax
0x18003f25c  jmp     loc_18003F1D3
0x18003f261  mov     hkey, rdi; pv
0x18003f264  call    cs:__imp_CoTaskMemFree
0x18003f26b  nop     dword ptr [rax+rax+00h]
0x18003f270  add     r14d, r14d
0x18003f273  jmp     loc_18003F1D3
0x18003f278  mov     esi, 8007000Eh
0x18003f27d  jmp     loc_18003F1D3
0x18003f282  mov     eax, [rdi+0Ch]
0x18003f285  lea     ecx, [rax+2]; cb
0x18003f288  cmp     ecx, eax
0x18003f28a  jb      short loc_18003F2CA
0x18003f28c  mov     esi, r13d
0x18003f28f  call    cs:__imp_CoTaskMemAlloc
0x18003f296  nop     dword ptr [rax+rax+00h]
0x18003f29b  mov     rbx, rax
0x18003f29e  test    rax, rax
0x18003f2a1  jz      short loc_18003F2C3
0x18003f2a3  mov     r8d, [rdi+0Ch]; Size
0x18003f2a7  lea     rdx, [rdi+10h]; Src
0x18003f2ab  mov     hkey, rax; void *
0x18003f2ae  call    memcpy_0
0x18003f2b3  mov     ecx, [rdi+0Ch]
0x18003f2b6  shr     hkey, 1
0x18003f2b9  mov     [rbx+hkey*2], r13w
0x18003f2be  mov     [r15], rbx
0x18003f2c1  jmp     short loc_18003F2D6
0x18003f2c3  mov     esi, 8007000Eh
0x18003f2c8  jmp     short loc_18003F2D6
0x18003f2ca  mov     esi, 80070216h
0x18003f2cf  jmp     short loc_18003F2D6
0x18003f2d1  test    rdi, rdi
0x18003f2d4  jz      short loc_18003F2E5
0x18003f2d6  mov     hkey, rdi; pv
0x18003f2d9  call    cs:__imp_CoTaskMemFree
0x18003f2e0  nop     dword ptr [rax+rax+00h]
0x18003f2e5  mov     rbx, [rsp+58h+arg_0]
0x18003f2ea  mov     eax, esi
0x18003f2ec  mov     rsi, [rsp+58h+arg_18]
0x18003f2f1  mov     rbp, [rsp+58h+arg_8]
0x18003f2f6  add     rsp, 30h
0x18003f2fa  pop     r15
0x18003f2fc  pop     r14
0x18003f2fe  pop     r13
0x18003f300  pop     r12
0x18003f302  pop     rdi
0x18003f303  retn
```
