# RtlpFileIsWin32WithRCManifest

- ea: `0x1800fb630`
- end: `0x1800fb938`
- name: `RtlpFileIsWin32WithRCManifest`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x18007a2c0`

## callees

- `0x18001861c`
- `0x18001c520`
- `0x18001f070`
- `0x18002a5b0`
- `0x1800723a0`
- `0x1800743b0`
- `0x180079050`
- `0x1800fb630`
- `0x18015ecc0`
- `0x18015efe0`
- `0x18015f020`
- `0x18015f420`
- `0x18015f580`
- `0x180162810`

## pseudocode

```c
char __fastcall RtlpFileIsWin32WithRCManifest(__int64 a1)
{
  char v1; // di
  char v2; // r14
  __int64 v3; // rbx
  __int64 v4; // rdx
  int v5; // esi
  int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v9; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v10; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h]
  HANDLE v12; // [rsp+78h] [rbp-88h] BYREF
  __int128 v13; // [rsp+80h] [rbp-80h] BYREF
  __m128i v14; // [rsp+90h] [rbp-70h] BYREF
  __int64 v15; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v16; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD *v17; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v18; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v19; // [rsp+C8h] [rbp-38h]
  _BYTE v20[48]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v21; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v22[3]; // [rsp+118h] [rbp+18h] BYREF

  v1 = 0;
  v15 = 0;
  v12 = 0;
  Handle = 0;
  v2 = 0;
  v9 = 0;
  v17 = 0;
  v10 = 0;
  v13 = 0;
  v16 = 0;
  memset(v20, 0, 44);
  v21 = 0;
  v18 = 0;
  v19 = 0;
  v14 = 0;
  if ( (int)RtlInitUnicodeStringEx(&v14, a1) >= 0
    && (int)RtlpDosPathNameToRelativeNtPathName(2, &v14, 0, (unsigned __int16 *)&v13, 0, 0, (__int64)&v18) >= 0 )
  {
    v3 = *((_QWORD *)&v13 + 1);
    if ( (_WORD)v18 )
    {
      v4 = v19;
      v13 = v18;
    }
    else
    {
      v4 = 0;
      *(_QWORD *)&v19 = 0;
    }
    *(_DWORD *)v20 = 48;
    *(_DWORD *)&v20[24] = 64;
    *(_QWORD *)&v20[8] = v4 & -(__int64)(v3 != 0);
    *(_QWORD *)&v20[16] = &v13;
    *(_OWORD *)&v20[32] = 0;
    v5 = ZwCreateFile(&v12, 2148532352LL, v20, &v21, 0, 0, 5, 1, 0, 0, 0);
    if ( v3 )
    {
      RtlReleaseRelativeName(&v18);
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v3);
    }
    if ( v5 >= 0 )
    {
      v2 = 1;
      if ( (int)NtCreateSection() >= 0 )
      {
        v10 = 0;
        v15 = 0;
        v9 = 0;
        v6 = ZwMapViewOfSection(Handle, -1, &v9, 0, 0, &v10, &v15, 1, 0, 8);
        NtClose(Handle);
        if ( v6 >= 0 )
        {
          v14.m128i_i64[0] = 0;
          RtlImageNtHeaderEx(1, v9, 0, &v14);
          if ( v14.m128i_i64[0] )
          {
            v22[0] = L"MUI";
            v22[1] = 1;
            v7 = v9 | 1;
            v22[2] = 0;
            if ( (int)LdrpSearchResourceSection_U((unsigned int)v9 | 1, (unsigned int)v22, 3, 48, (__int64)&v16) >= 0
              && (int)LdrpAccessResourceDataNoMultipleLanguage(v7, v16, (unsigned __int64 *)&v17, &v14) >= 0
              && *v17 == -20054323 )
            {
              v1 = 1;
            }
          }
        }
      }
    }
  }
  if ( v9 )
    NtUnmapViewOfSection(-1);
  if ( v2 )
    NtClose(v12);
  return v1;
}

```

## disassembly

```asm
0x1800fb630  mov     [rsp-8+arg_8], rbx
0x1800fb635  mov     [rsp-8+arg_10], rsi
0x1800fb63a  push    rbp
0x1800fb63b  push    rdi
0x1800fb63c  push    r12
0x1800fb63e  push    r14
0x1800fb640  push    r15
0x1800fb642  lea     rbp, [rsp-40h]
0x1800fb647  sub     rsp, 140h
0x1800fb64e  mov     rax, cs:__security_cookie
0x1800fb655  xor     rax, rsp
0x1800fb658  mov     [rbp+60h+var_30], rax
0x1800fb65c  xor     r15d, r15d
0x1800fb65f  xorps   xmm0, xmm0
0x1800fb662  xorps   xmm1, xmm1
0x1800fb665  movzx   edi, r15b
0x1800fb669  mov     rdx, rcx
0x1800fb66c  mov     [rbp+60h+var_C0], r15
0x1800fb670  movups  [rbp+60h+var_78], xmm0
0x1800fb674  xor     eax, eax
0x1800fb676  mov     [rsp+160h+var_E8], r15
0x1800fb67b  lea     rcx, [rbp+60h+var_D0]
0x1800fb67f  mov     [rsp+160h+Handle], r15
0x1800fb684  movups  [rbp+60h+var_78+0Ch], xmm0
0x1800fb688  mov     r14b, r15b
0x1800fb68b  mov     [rsp+160h+var_100], r15
0x1800fb690  mov     [rbp+60h+var_B0], r15
0x1800fb694  mov     [rsp+160h+var_F8], r15
0x1800fb699  movups  [rbp+60h+var_E0], xmm0
0x1800fb69d  mov     [rbp+60h+var_B8], r15
0x1800fb6a1  movups  [rbp+60h+var_88], xmm0
0x1800fb6a5  movups  [rbp+60h+var_58], xmm0
0x1800fb6a9  movups  [rbp+60h+var_A8], xmm1
0x1800fb6ad  movups  [rbp+60h+var_98], xmm1
0x1800fb6b1  movups  [rbp+60h+var_D0], xmm0
0x1800fb6b5  call    RtlInitUnicodeStringEx
0x1800fb6ba  test    eax, eax
0x1800fb6bc  js      loc_1800FB8C7
0x1800fb6c2  lea     rax, [rbp+60h+var_A8]
0x1800fb6c6  xor     r8d, r8d
0x1800fb6c9  mov     [rsp+160h+var_130], rax
0x1800fb6ce  lea     r9, [rbp+60h+var_E0]
0x1800fb6d2  mov     [rsp+160h+var_138], r15
0x1800fb6d7  lea     rdx, [rbp+60h+var_D0]
0x1800fb6db  lea     ecx, [r15+2]
0x1800fb6df  mov     [rsp+160h+var_140], r15
0x1800fb6e4  call    RtlpDosPathNameToRelativeNtPathName
0x1800fb6e9  test    eax, eax
0x1800fb6eb  js      loc_1800FB8C7
0x1800fb6f1  movzx   eax, word ptr [rbp+60h+var_A8]
0x1800fb6f5  mov     rbx, qword ptr [rbp+60h+var_E0+8]
0x1800fb6f9  test    ax, ax
0x1800fb6fc  jnz     loc_1800FB915
0x1800fb702  mov     edx, r15d
0x1800fb705  mov     qword ptr [rbp+60h+var_98], rdx
0x1800fb709  mov     [rsp+160h+var_110], r15d
0x1800fb70e  lea     r9, [rbp+60h+var_58]
0x1800fb712  mov     [rsp+160h+var_118], r15
0x1800fb717  lea     r8, [rbp+60h+var_88]
0x1800fb71b  mov     [rsp+160h+var_120], r15d
0x1800fb720  xorps   xmm0, xmm0
0x1800fb723  mov     rax, rbx
0x1800fb726  mov     dword ptr [rbp+60h+var_88], 30h ; '0'
0x1800fb72d  neg     rax
0x1800fb730  mov     dword ptr [rbp+60h+var_78+8], 40h ; '@'
0x1800fb737  lea     rax, [rbp+60h+var_E0]
0x1800fb73b  mov     r12d, 1
0x1800fb741  sbb     rcx, rcx
0x1800fb744  mov     [rsp+160h+var_128], r12d
0x1800fb749  and     rcx, rdx
0x1800fb74c  mov     dword ptr [rsp+160h+var_130], 5
0x1800fb754  mov     qword ptr [rbp+60h+var_88+8], rcx
0x1800fb758  mov     edx, 80100080h
0x1800fb75d  lea     rcx, [rsp+160h+var_E8]
0x1800fb762  mov     dword ptr [rsp+160h+var_138], r15d
0x1800fb767  mov     qword ptr [rbp+60h+var_78], rax
0x1800fb76b  movdqu  [rbp+60h+var_68], xmm0
0x1800fb770  mov     [rsp+160h+var_140], r15
0x1800fb775  call    ZwCreateFile
0x1800fb77a  mov     esi, eax
0x1800fb77c  test    rbx, rbx
0x1800fb77f  jz      short loc_1800FB7A1
0x1800fb781  lea     rcx, [rbp+60h+var_A8]
0x1800fb785  call    RtlReleaseRelativeName
0x1800fb78a  mov     rcx, gs:60h
0x1800fb793  mov     r8, rbx
0x1800fb796  xor     edx, edx
0x1800fb798  mov     rcx, [rcx+30h]
0x1800fb79c  call    RtlFreeHeap_0
0x1800fb7a1  test    esi, esi
0x1800fb7a3  js      loc_1800FB8C7
0x1800fb7a9  mov     rax, [rsp+160h+var_E8]
0x1800fb7ae  lea     rcx, [rsp+160h+Handle]
0x1800fb7b3  mov     [rsp+160h+var_130], rax
0x1800fb7b8  xor     r9d, r9d
0x1800fb7bb  mov     dword ptr [rsp+160h+var_138], 8000000h
0x1800fb7c3  xor     r8d, r8d
0x1800fb7c6  mov     edx, 0F0005h
0x1800fb7cb  mov     dword ptr [rsp+160h+var_140], 2
0x1800fb7d3  mov     r14b, r12b
0x1800fb7d6  call    NtCreateSection
0x1800fb7db  test    eax, eax
0x1800fb7dd  js      loc_1800FB8C7
0x1800fb7e3  mov     rcx, [rsp+160h+Handle]
0x1800fb7e8  lea     rax, [rbp+60h+var_C0]
0x1800fb7ec  mov     dword ptr [rsp+160h+var_118], 8
0x1800fb7f4  lea     r8, [rsp+160h+var_100]
0x1800fb7f9  mov     [rsp+160h+var_120], r15d
0x1800fb7fe  xor     r9d, r9d
0x1800fb801  mov     [rsp+160h+var_128], r12d
0x1800fb806  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fb80a  mov     [rsp+160h+var_130], rax
0x1800fb80f  lea     rax, [rsp+160h+var_F8]
0x1800fb814  mov     [rsp+160h+var_138], rax
0x1800fb819  mov     [rsp+160h+var_140], r15
0x1800fb81e  mov     [rsp+160h+var_F8], r15
0x1800fb823  mov     [rbp+60h+var_C0], r15
0x1800fb827  mov     [rsp+160h+var_100], r15
0x1800fb82c  call    ZwMapViewOfSection
0x1800fb831  mov     rcx, [rsp+160h+Handle]; Handle
0x1800fb836  mov     ebx, eax
0x1800fb838  call    NtClose
0x1800fb83d  test    ebx, ebx
0x1800fb83f  js      loc_1800FB8C7
0x1800fb845  mov     rdx, [rsp+160h+var_100]
0x1800fb84a  lea     r9, [rbp+60h+var_D0]
0x1800fb84e  xor     r8d, r8d
0x1800fb851  mov     qword ptr [rbp+60h+var_D0], r15
0x1800fb855  mov     ecx, r12d
0x1800fb858  call    RtlImageNtHeaderEx
0x1800fb85d  cmp     qword ptr [rbp+60h+var_D0], r15
0x1800fb861  jz      short loc_1800FB8C7
0x1800fb863  mov     rbx, [rsp+160h+var_100]
0x1800fb868  lea     rax, aMui; "MUI"
0x1800fb86f  mov     r9d, 30h ; '0'
0x1800fb875  mov     [rbp+60h+var_48], rax
0x1800fb879  lea     rax, [rbp+60h+var_B8]
0x1800fb87d  mov     [rbp+60h+var_40], r12
0x1800fb881  or      rbx, r12
0x1800fb884  mov     [rbp+60h+var_38], r15
0x1800fb888  lea     rdx, [rbp+60h+var_48]
0x1800fb88c  mov     [rsp+160h+var_140], rax
0x1800fb891  lea     r8d, [r9-2Dh]
0x1800fb895  mov     rcx, rbx
0x1800fb898  call    LdrpSearchResourceSection_U
0x1800fb89d  test    eax, eax
0x1800fb89f  js      short loc_1800FB8C7
0x1800fb8a1  mov     rdx, [rbp+60h+var_B8]
0x1800fb8a5  lea     r9, [rbp+60h+var_D0]
0x1800fb8a9  lea     r8, [rbp+60h+var_B0]
0x1800fb8ad  mov     rcx, rbx
0x1800fb8b0  call    LdrpAccessResourceDataNoMultipleLanguage
0x1800fb8b5  test    eax, eax
0x1800fb8b7  js      short loc_1800FB8C7
0x1800fb8b9  mov     rax, [rbp+60h+var_B0]
0x1800fb8bd  cmp     dword ptr [rax], 0FECDFECDh
0x1800fb8c3  cmovz   edi, r12d
0x1800fb8c7  mov     rdx, [rsp+160h+var_100]
0x1800fb8cc  test    rdx, rdx
0x1800fb8cf  jz      short loc_1800FB8DA
0x1800fb8d1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800fb8d5  call    NtUnmapViewOfSection
0x1800fb8da  test    r14b, r14b
0x1800fb8dd  jz      short loc_1800FB8E9
0x1800fb8df  mov     rcx, [rsp+160h+var_E8]; Handle
0x1800fb8e4  call    NtClose
0x1800fb8e9  mov     al, dil
0x1800fb8ec  mov     rcx, [rbp+60h+var_30]
0x1800fb8f0  xor     rcx, rsp; StackCookie
0x1800fb8f3  call    __security_check_cookie
0x1800fb8f8  lea     r11, [rsp+160h+var_20]
0x1800fb900  mov     rbx, [r11+38h]
0x1800fb904  mov     rsi, [r11+40h]
0x1800fb908  mov     rsp, r11
0x1800fb90b  pop     r15
0x1800fb90d  pop     r14
0x1800fb90f  pop     r12
0x1800fb911  pop     rdi
0x1800fb912  pop     rbp
0x1800fb913  retn
0x1800fb915  mov     rdx, qword ptr [rbp+60h+var_98]
0x1800fb919  mov     word ptr [rbp+60h+var_E0], ax
0x1800fb91d  mov     eax, dword ptr [rbp+60h+var_A8+2]
0x1800fb920  mov     dword ptr [rbp+60h+var_E0+2], eax
0x1800fb923  movzx   eax, word ptr [rbp+60h+var_A8+6]
0x1800fb927  mov     word ptr [rbp+60h+var_E0+6], ax
0x1800fb92b  mov     rax, qword ptr [rbp+60h+var_A8+8]
0x1800fb92f  mov     qword ptr [rbp+60h+var_E0+8], rax
0x1800fb933  jmp     loc_1800FB709
```
