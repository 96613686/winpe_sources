# RtlpLoadInstallLanguageFallback

- ea: `0x1800b88e8`
- end: `0x1800b8c3e`
- name: `RtlpLoadInstallLanguageFallback`
- size: `854`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18000acb0`
- `0x18000c9a0`
- `0x18000ee60`
- `0x1801205f0`
- `0x18014d654`

## callees

- `0x18000b730`
- `0x18001861c`
- `0x18001b984`
- `0x1800b88e8`
- `0x1800b8f30`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180163a80`
- `0x18016f030`

## string_xrefs

- `0x1800b895b`: `\Registry\Machine\System\CurrentControlSet\Control\NLS\Language`
- `0x1800b89de`: `InstallLanguageFallback`

## pseudocode

```c
__int64 __fastcall RtlpLoadInstallLanguageFallback(__int64 a1, _WORD *a2, _WORD *a3)
{
  void *v5; // rax
  void *v6; // rsi
  size_t v7; // rax
  int v8; // ebx
  HANDLE v9; // rbx
  size_t v10; // rax
  _DWORD *Heap_0; // rdi
  int v12; // eax
  int v13; // r15d
  const wchar_t *i; // rdi
  __int16 *v15; // rcx
  size_t v17; // rax
  size_t v18; // rax
  __int16 v19; // ax
  HANDLE Handle; // [rsp+30h] [rbp-50h] BYREF
  __int128 v21; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v22[4]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v23; // [rsp+68h] [rbp-18h]
  int v24; // [rsp+C0h] [rbp+40h] BYREF
  int v25; // [rsp+D8h] [rbp+58h] BYREF

  Handle = 0;
  v24 = 0;
  v21 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v6 = 0;
    v8 = -1073741811;
    goto LABEL_24;
  }
  v5 = (void *)MuiRegAllocArray(a1, 172);
  v6 = v5;
  if ( !v5 )
  {
    v8 = -1073741801;
    goto LABEL_24;
  }
  memset_thunk_772440563353939046(v5, 0, 0x158u);
  *a2 = 0;
  *((_QWORD *)&v21 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language";
  *a3 = 0;
  *(_QWORD *)&v21 = 0;
  v7 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\NLS\\Language");
  v22[0] = 48;
  v22[3] = 64;
  Handle = 0;
  v22[1] = 0;
  v23 = 0;
  if ( v7 >= 0xFFFE )
    LOWORD(v7) = -4;
  LOWORD(v21) = v7;
  WORD1(v21) = v7 + 2;
  v22[2] = &v21;
  v8 = NtOpenKey(&Handle, 131097, v22);
  if ( v8 >= 0 )
  {
    *(_QWORD *)&v21 = 0;
    *((_QWORD *)&v21 + 1) = L"InstallLanguageFallback";
    v9 = Handle;
    v10 = 2 * wcslen(L"InstallLanguageFallback");
    v25 = 0;
    if ( v10 >= 0xFFFE )
      LOWORD(v10) = -4;
    LOWORD(v21) = v10;
    WORD1(v21) = v10 + 2;
    Heap_0 = (_DWORD *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 356);
    if ( !Heap_0 )
    {
      v8 = -1073741670;
      goto LABEL_24;
    }
    v12 = NtQueryValueKey(v9, &v21, 2, Heap_0, 356, &v25);
    v8 = v12;
    if ( v12 >= 0 )
    {
      if ( Heap_0[2] > 0x158u )
        v8 = -2147483643;
      else
        memmove(v6, Heap_0 + 3, (unsigned int)Heap_0[2]);
    }
    else
    {
      v13 = 0;
      if ( v12 != -2147483643 )
      {
LABEL_17:
        RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
        if ( v8 >= 0 )
        {
          if ( v13 != 1 )
            goto LABEL_45;
          for ( i = (const wchar_t *)v6; *i; ++i )
          {
            v15 = (__int16 *)(i + 1);
            if ( *i == 44 )
            {
              *i++ = 0;
              v19 = *v15;
              if ( *v15 )
              {
                do
                {
                  if ( v19 != 32 )
                    break;
                  v19 = *++i;
                }
                while ( *i );
              }
              break;
            }
          }
          *(_QWORD *)&v21 = 0;
          *((_QWORD *)&v21 + 1) = v6;
          v17 = 2 * wcslen((const wchar_t *)v6);
          if ( v17 >= 0xFFFE )
            LOWORD(v17) = -4;
          LOWORD(v21) = v17;
          WORD1(v21) = v17 + 2;
          if ( (unsigned __int8)RtlCultureNameToLCID(&v21, &v24) )
          {
            *a2 = v24;
            if ( *i )
            {
              *(_QWORD *)&v21 = 0;
              *((_QWORD *)&v21 + 1) = i;
              v18 = 2 * wcslen(i);
              if ( v18 >= 0xFFFE )
                LOWORD(v18) = -4;
              LOWORD(v21) = v18;
              WORD1(v21) = v18 + 2;
              if ( (unsigned __int8)RtlCultureNameToLCID(&v21, &v24) )
              {
                *a3 = v24;
              }
              else
              {
                v8 = -1073741823;
                *a2 = 0;
              }
            }
          }
          else
          {
LABEL_45:
            v8 = -1073741823;
          }
        }
        goto LABEL_24;
      }
    }
    v13 = Heap_0[1];
    goto LABEL_17;
  }
LABEL_24:
  if ( Handle )
    NtClose(Handle);
  if ( v6 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800b88e8  mov     [rsp-38h+arg_8], rbx
0x1800b88ed  push    rbp
0x1800b88ee  push    rsi
0x1800b88ef  push    rdi
0x1800b88f0  push    r12
0x1800b88f2  push    r13
0x1800b88f4  push    r14
0x1800b88f6  push    r15
0x1800b88f8  mov     rbp, rsp
0x1800b88fb  sub     rsp, 80h
0x1800b8902  xor     r13d, r13d
0x1800b8905  xorps   xmm0, xmm0
0x1800b8908  mov     [rbp+Handle], r13
0x1800b890c  mov     r12, r8
0x1800b890f  mov     [rbp+arg_0], r13d
0x1800b8913  mov     r14, rdx
0x1800b8916  movups  [rbp+var_48], xmm0
0x1800b891a  test    rcx, rcx
0x1800b891d  jz      loc_1800B8AD4
0x1800b8923  test    rdx, rdx
0x1800b8926  jz      loc_1800B8AD4
0x1800b892c  test    r8, r8
0x1800b892f  jz      loc_1800B8AD4
0x1800b8935  mov     edx, 0ACh
0x1800b893a  call    _MuiRegAllocArray
0x1800b893f  mov     rsi, rax
0x1800b8942  test    rax, rax
0x1800b8945  jz      loc_1800B8BB9
0x1800b894b  xor     edx, edx; Val
0x1800b894d  mov     r8d, 158h; Size
0x1800b8953  mov     rcx, rax; void *
0x1800b8956  call    memset$thunk$772440563353939046
0x1800b895b  lea     rcx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800b8962  mov     [r14], r13w
0x1800b8966  mov     qword ptr [rbp+var_48+8], rcx
0x1800b896a  mov     [r12], r13w
0x1800b896f  mov     qword ptr [rbp+var_48], r13
0x1800b8973  call    wcslen
0x1800b8978  add     rax, rax
0x1800b897b  mov     [rbp+var_38], 30h ; '0'
0x1800b8983  mov     ecx, 0FFFCh
0x1800b8988  mov     [rbp+var_20], 40h ; '@'
0x1800b8990  xorps   xmm0, xmm0
0x1800b8993  mov     [rbp+Handle], r13
0x1800b8997  lea     r15d, [r13+2]
0x1800b899b  mov     [rbp+var_30], r13
0x1800b899f  lea     r8, [rbp+var_38]
0x1800b89a3  mov     edx, 20019h
0x1800b89a8  lea     edi, [rcx+2]
0x1800b89ab  cmp     rax, rdi
0x1800b89ae  movdqu  [rbp+var_18], xmm0
0x1800b89b3  cmovnb  rax, rcx
0x1800b89b7  lea     rcx, [rbp+Handle]
0x1800b89bb  mov     word ptr [rbp+var_48], ax
0x1800b89bf  add     ax, r15w
0x1800b89c3  mov     word ptr [rbp+var_48+2], ax
0x1800b89c7  lea     rax, [rbp+var_48]
0x1800b89cb  mov     [rbp+var_28], rax
0x1800b89cf  call    NtOpenKey
0x1800b89d4  mov     ebx, eax
0x1800b89d6  test    eax, eax
0x1800b89d8  js      loc_1800B8ADC
0x1800b89de  lea     rcx, aInstalllanguag; "InstallLanguageFallback"
0x1800b89e5  mov     qword ptr [rbp+var_48], r13
0x1800b89e9  mov     qword ptr [rbp+var_48+8], rcx
0x1800b89ed  call    wcslen
0x1800b89f2  mov     rbx, [rbp+Handle]
0x1800b89f6  lea     ecx, [rdi-2]
0x1800b89f9  add     rax, rax
0x1800b89fc  mov     [rbp+arg_18], r13d
0x1800b8a00  cmp     rax, rdi
0x1800b8a03  lea     edx, [r13+8]
0x1800b8a07  mov     r8d, 164h
0x1800b8a0d  cmovnb  rax, rcx
0x1800b8a11  mov     word ptr [rbp+var_48], ax
0x1800b8a15  add     ax, r15w
0x1800b8a19  mov     word ptr [rbp+var_48+2], ax
0x1800b8a1d  mov     rcx, gs:60h
0x1800b8a26  mov     rcx, [rcx+30h]
0x1800b8a2a  call    RtlAllocateHeap_0
0x1800b8a2f  mov     rdi, rax
0x1800b8a32  test    rax, rax
0x1800b8a35  jz      loc_1800B8C2A
0x1800b8a3b  lea     rax, [rbp+arg_18]
0x1800b8a3f  mov     r9, rdi
0x1800b8a42  mov     [rsp+80h+var_58], rax
0x1800b8a47  lea     rdx, [rbp+var_48]
0x1800b8a4b  mov     r8d, r15d
0x1800b8a4e  mov     [rsp+80h+var_60], 164h
0x1800b8a56  mov     rcx, rbx
0x1800b8a59  call    NtQueryValueKey
0x1800b8a5e  mov     ebx, eax
0x1800b8a60  test    eax, eax
0x1800b8a62  jns     short loc_1800B8A70
0x1800b8a64  mov     r15d, r13d
0x1800b8a67  cmp     eax, 80000005h
0x1800b8a6c  jz      short loc_1800B8A8D
0x1800b8a6e  jmp     short loc_1800B8A91
0x1800b8a70  cmp     dword ptr [rdi+8], 158h
0x1800b8a77  ja      loc_1800B8C20
0x1800b8a7d  mov     r8d, [rdi+8]; Size
0x1800b8a81  lea     rdx, [rdi+0Ch]; Src
0x1800b8a85  mov     rcx, rsi; void *
0x1800b8a88  call    memmove
0x1800b8a8d  mov     r15d, [rdi+4]
0x1800b8a91  mov     rcx, gs:60h
0x1800b8a9a  mov     r8, rdi
0x1800b8a9d  xor     edx, edx
0x1800b8a9f  mov     rcx, [rcx+30h]
0x1800b8aa3  call    RtlFreeHeap_0
0x1800b8aa8  test    ebx, ebx
0x1800b8aaa  js      short loc_1800B8ADC
0x1800b8aac  cmp     r15d, 1
0x1800b8ab0  jnz     loc_1800B8C34
0x1800b8ab6  mov     rdi, rsi
0x1800b8ab9  movzx   eax, word ptr [rdi]
0x1800b8abc  test    ax, ax
0x1800b8abf  jz      short loc_1800B8B11
0x1800b8ac1  lea     rcx, [rdi+2]
0x1800b8ac5  cmp     ax, 2Ch ; ','
0x1800b8ac9  jz      loc_1800B8BC3
0x1800b8acf  mov     rdi, rcx
0x1800b8ad2  jmp     short loc_1800B8AB9
0x1800b8ad4  mov     rsi, r13
0x1800b8ad7  mov     ebx, 0C000000Dh
0x1800b8adc  mov     rcx, [rbp+Handle]; Handle
0x1800b8ae0  test    rcx, rcx
0x1800b8ae3  jz      short loc_1800B8AEA
0x1800b8ae5  call    NtClose
0x1800b8aea  test    rsi, rsi
0x1800b8aed  jnz     loc_1800B8C04
0x1800b8af3  mov     eax, ebx
0x1800b8af5  mov     rbx, [rsp+80h+arg_8]
0x1800b8afd  add     rsp, 80h
0x1800b8b04  pop     r15
0x1800b8b06  pop     r14
0x1800b8b08  pop     r13
0x1800b8b0a  pop     r12
0x1800b8b0c  pop     rdi
0x1800b8b0d  pop     rsi
0x1800b8b0e  pop     rbp
0x1800b8b0f  retn
0x1800b8b11  mov     r15d, 2
0x1800b8b17  mov     rcx, rsi; String
0x1800b8b1a  mov     qword ptr [rbp+var_48], r13
0x1800b8b1e  mov     qword ptr [rbp+var_48+8], rsi
0x1800b8b22  call    wcslen
0x1800b8b27  add     rax, rax
0x1800b8b2a  lea     rdx, [rbp+arg_0]
0x1800b8b2e  cmp     rax, 0FFFEh
0x1800b8b34  mov     ecx, 0FFFCh
0x1800b8b39  cmovnb  rax, rcx
0x1800b8b3d  lea     rcx, [rbp+var_48]
0x1800b8b41  mov     word ptr [rbp+var_48], ax
0x1800b8b45  add     ax, r15w
0x1800b8b49  mov     word ptr [rbp+var_48+2], ax
0x1800b8b4d  call    RtlCultureNameToLCID
0x1800b8b52  test    al, al
0x1800b8b54  jz      loc_1800B8C34
0x1800b8b5a  movzx   eax, word ptr [rbp+arg_0]
0x1800b8b5e  mov     [r14], ax
0x1800b8b62  cmp     [rdi], r13w
0x1800b8b66  jz      loc_1800B8ADC
0x1800b8b6c  mov     rcx, rdi; String
0x1800b8b6f  mov     qword ptr [rbp+var_48], r13
0x1800b8b73  mov     qword ptr [rbp+var_48+8], rdi
0x1800b8b77  call    wcslen
0x1800b8b7c  add     rax, rax
0x1800b8b7f  lea     rdx, [rbp+arg_0]
0x1800b8b83  cmp     rax, 0FFFEh
0x1800b8b89  mov     ecx, 0FFFCh
0x1800b8b8e  cmovnb  rax, rcx
0x1800b8b92  lea     rcx, [rbp+var_48]
0x1800b8b96  mov     word ptr [rbp+var_48], ax
0x1800b8b9a  add     ax, r15w
0x1800b8b9e  mov     word ptr [rbp+var_48+2], ax
0x1800b8ba2  call    RtlCultureNameToLCID
0x1800b8ba7  test    al, al
0x1800b8ba9  jnz     short loc_1800B8BF6
0x1800b8bab  mov     ebx, 0C0000001h
0x1800b8bb0  mov     [r14], r13w
0x1800b8bb4  jmp     loc_1800B8ADC
0x1800b8bb9  mov     ebx, 0C0000017h
0x1800b8bbe  jmp     loc_1800B8ADC
0x1800b8bc3  mov     [rdi], r13w
0x1800b8bc7  mov     rdi, rcx
0x1800b8bca  movzx   eax, word ptr [rcx]
0x1800b8bcd  test    ax, ax
0x1800b8bd0  jz      loc_1800B8B11
0x1800b8bd6  mov     r15d, 2
0x1800b8bdc  cmp     ax, 20h ; ' '
0x1800b8be0  jnz     loc_1800B8B17
0x1800b8be6  add     rdi, r15
0x1800b8be9  movzx   eax, word ptr [rdi]
0x1800b8bec  test    ax, ax
0x1800b8bef  jnz     short loc_1800B8BDC
0x1800b8bf1  jmp     loc_1800B8B17
0x1800b8bf6  movzx   eax, word ptr [rbp+arg_0]
0x1800b8bfa  mov     [r12], ax
0x1800b8bff  jmp     loc_1800B8ADC
0x1800b8c04  mov     rcx, gs:60h
0x1800b8c0d  mov     r8, rsi
0x1800b8c10  xor     edx, edx
0x1800b8c12  mov     rcx, [rcx+30h]
0x1800b8c16  call    RtlFreeHeap_0
0x1800b8c1b  jmp     loc_1800B8AF3
0x1800b8c20  mov     ebx, 80000005h
0x1800b8c25  jmp     loc_1800B8A8D
0x1800b8c2a  mov     ebx, 0C000009Ah
0x1800b8c2f  jmp     loc_1800B8ADC
0x1800b8c34  mov     ebx, 0C0000001h
0x1800b8c39  jmp     loc_1800B8ADC
```
