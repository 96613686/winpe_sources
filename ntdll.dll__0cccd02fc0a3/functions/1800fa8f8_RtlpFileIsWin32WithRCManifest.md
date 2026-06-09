# RtlpFileIsWin32WithRCManifest

- ea: `0x1800fa8f8`
- end: `0x1800fac00`
- name: `RtlpFileIsWin32WithRCManifest`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, service_task`

## callers

- `0x18005d8e0`

## callees

- `0x18001861c`
- `0x18001c520`
- `0x18001f070`
- `0x18002b2a0`
- `0x1800559c0`
- `0x1800579d0`
- `0x18005c670`
- `0x1800fa8f8`
- `0x18015e4b0`
- `0x18015e7d0`
- `0x18015e810`
- `0x18015ec10`
- `0x18015ed70`
- `0x180162000`

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
0x1800fa8f8  mov     [rsp-8+arg_8], rbx
0x1800fa8fd  mov     [rsp-8+arg_10], rsi
0x1800fa902  push    rbp
0x1800fa903  push    rdi
0x1800fa904  push    r12
0x1800fa906  push    r14
0x1800fa908  push    r15
0x1800fa90a  lea     rbp, [rsp-40h]
0x1800fa90f  sub     rsp, 140h
0x1800fa916  mov     rax, cs:__security_cookie
0x1800fa91d  xor     rax, rsp
0x1800fa920  mov     [rbp+60h+var_30], rax
0x1800fa924  xor     r15d, r15d
0x1800fa927  xorps   xmm0, xmm0
0x1800fa92a  xorps   xmm1, xmm1
0x1800fa92d  movzx   edi, r15b
0x1800fa931  mov     rdx, rcx
0x1800fa934  mov     [rbp+60h+var_C0], r15
0x1800fa938  movups  [rbp+60h+var_78], xmm0
0x1800fa93c  xor     eax, eax
0x1800fa93e  mov     [rsp+160h+var_E8], r15
0x1800fa943  lea     rcx, [rbp+60h+var_D0]
0x1800fa947  mov     [rsp+160h+Handle], r15
0x1800fa94c  movups  [rbp+60h+var_78+0Ch], xmm0
0x1800fa950  mov     r14b, r15b
0x1800fa953  mov     [rsp+160h+var_100], r15
0x1800fa958  mov     [rbp+60h+var_B0], r15
0x1800fa95c  mov     [rsp+160h+var_F8], r15
0x1800fa961  movups  [rbp+60h+var_E0], xmm0
0x1800fa965  mov     [rbp+60h+var_B8], r15
0x1800fa969  movups  [rbp+60h+var_88], xmm0
0x1800fa96d  movups  [rbp+60h+var_58], xmm0
0x1800fa971  movups  [rbp+60h+var_A8], xmm1
0x1800fa975  movups  [rbp+60h+var_98], xmm1
0x1800fa979  movups  [rbp+60h+var_D0], xmm0
0x1800fa97d  call    RtlInitUnicodeStringEx
0x1800fa982  test    eax, eax
0x1800fa984  js      loc_1800FAB8F
0x1800fa98a  lea     rax, [rbp+60h+var_A8]
0x1800fa98e  xor     r8d, r8d
0x1800fa991  mov     [rsp+160h+var_130], rax
0x1800fa996  lea     r9, [rbp+60h+var_E0]
0x1800fa99a  mov     [rsp+160h+var_138], r15
0x1800fa99f  lea     rdx, [rbp+60h+var_D0]
0x1800fa9a3  lea     ecx, [r15+2]
0x1800fa9a7  mov     [rsp+160h+var_140], r15
0x1800fa9ac  call    RtlpDosPathNameToRelativeNtPathName
0x1800fa9b1  test    eax, eax
0x1800fa9b3  js      loc_1800FAB8F
0x1800fa9b9  movzx   eax, word ptr [rbp+60h+var_A8]
0x1800fa9bd  mov     rbx, qword ptr [rbp+60h+var_E0+8]
0x1800fa9c1  test    ax, ax
0x1800fa9c4  jnz     loc_1800FABDD
0x1800fa9ca  mov     edx, r15d
0x1800fa9cd  mov     qword ptr [rbp+60h+var_98], rdx
0x1800fa9d1  mov     [rsp+160h+var_110], r15d
0x1800fa9d6  lea     r9, [rbp+60h+var_58]
0x1800fa9da  mov     [rsp+160h+var_118], r15
0x1800fa9df  lea     r8, [rbp+60h+var_88]
0x1800fa9e3  mov     [rsp+160h+var_120], r15d
0x1800fa9e8  xorps   xmm0, xmm0
0x1800fa9eb  mov     rax, rbx
0x1800fa9ee  mov     dword ptr [rbp+60h+var_88], 30h ; '0'
0x1800fa9f5  neg     rax
0x1800fa9f8  mov     dword ptr [rbp+60h+var_78+8], 40h ; '@'
0x1800fa9ff  lea     rax, [rbp+60h+var_E0]
0x1800faa03  mov     r12d, 1
0x1800faa09  sbb     rcx, rcx
0x1800faa0c  mov     [rsp+160h+var_128], r12d
0x1800faa11  and     rcx, rdx
0x1800faa14  mov     dword ptr [rsp+160h+var_130], 5
0x1800faa1c  mov     qword ptr [rbp+60h+var_88+8], rcx
0x1800faa20  mov     edx, 80100080h
0x1800faa25  lea     rcx, [rsp+160h+var_E8]
0x1800faa2a  mov     dword ptr [rsp+160h+var_138], r15d
0x1800faa2f  mov     qword ptr [rbp+60h+var_78], rax
0x1800faa33  movdqu  [rbp+60h+var_68], xmm0
0x1800faa38  mov     [rsp+160h+var_140], r15
0x1800faa3d  call    ZwCreateFile
0x1800faa42  mov     esi, eax
0x1800faa44  test    rbx, rbx
0x1800faa47  jz      short loc_1800FAA69
0x1800faa49  lea     rcx, [rbp+60h+var_A8]
0x1800faa4d  call    RtlReleaseRelativeName
0x1800faa52  mov     rcx, gs:60h
0x1800faa5b  mov     r8, rbx
0x1800faa5e  xor     edx, edx
0x1800faa60  mov     rcx, [rcx+30h]
0x1800faa64  call    RtlFreeHeap_0
0x1800faa69  test    esi, esi
0x1800faa6b  js      loc_1800FAB8F
0x1800faa71  mov     rax, [rsp+160h+var_E8]
0x1800faa76  lea     rcx, [rsp+160h+Handle]
0x1800faa7b  mov     [rsp+160h+var_130], rax
0x1800faa80  xor     r9d, r9d
0x1800faa83  mov     dword ptr [rsp+160h+var_138], 8000000h
0x1800faa8b  xor     r8d, r8d
0x1800faa8e  mov     edx, 0F0005h
0x1800faa93  mov     dword ptr [rsp+160h+var_140], 2
0x1800faa9b  mov     r14b, r12b
0x1800faa9e  call    NtCreateSection
0x1800faaa3  test    eax, eax
0x1800faaa5  js      loc_1800FAB8F
0x1800faaab  mov     rcx, [rsp+160h+Handle]
0x1800faab0  lea     rax, [rbp+60h+var_C0]
0x1800faab4  mov     dword ptr [rsp+160h+var_118], 8
0x1800faabc  lea     r8, [rsp+160h+var_100]
0x1800faac1  mov     [rsp+160h+var_120], r15d
0x1800faac6  xor     r9d, r9d
0x1800faac9  mov     [rsp+160h+var_128], r12d
0x1800faace  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800faad2  mov     [rsp+160h+var_130], rax
0x1800faad7  lea     rax, [rsp+160h+var_F8]
0x1800faadc  mov     [rsp+160h+var_138], rax
0x1800faae1  mov     [rsp+160h+var_140], r15
0x1800faae6  mov     [rsp+160h+var_F8], r15
0x1800faaeb  mov     [rbp+60h+var_C0], r15
0x1800faaef  mov     [rsp+160h+var_100], r15
0x1800faaf4  call    ZwMapViewOfSection
0x1800faaf9  mov     rcx, [rsp+160h+Handle]; Handle
0x1800faafe  mov     ebx, eax
0x1800fab00  call    NtClose
0x1800fab05  test    ebx, ebx
0x1800fab07  js      loc_1800FAB8F
0x1800fab0d  mov     rdx, [rsp+160h+var_100]
0x1800fab12  lea     r9, [rbp+60h+var_D0]
0x1800fab16  xor     r8d, r8d
0x1800fab19  mov     qword ptr [rbp+60h+var_D0], r15
0x1800fab1d  mov     ecx, r12d
0x1800fab20  call    RtlImageNtHeaderEx
0x1800fab25  cmp     qword ptr [rbp+60h+var_D0], r15
0x1800fab29  jz      short loc_1800FAB8F
0x1800fab2b  mov     rbx, [rsp+160h+var_100]
0x1800fab30  lea     rax, aMui; "MUI"
0x1800fab37  mov     r9d, 30h ; '0'
0x1800fab3d  mov     [rbp+60h+var_48], rax
0x1800fab41  lea     rax, [rbp+60h+var_B8]
0x1800fab45  mov     [rbp+60h+var_40], r12
0x1800fab49  or      rbx, r12
0x1800fab4c  mov     [rbp+60h+var_38], r15
0x1800fab50  lea     rdx, [rbp+60h+var_48]
0x1800fab54  mov     [rsp+160h+var_140], rax
0x1800fab59  lea     r8d, [r9-2Dh]
0x1800fab5d  mov     rcx, rbx
0x1800fab60  call    LdrpSearchResourceSection_U
0x1800fab65  test    eax, eax
0x1800fab67  js      short loc_1800FAB8F
0x1800fab69  mov     rdx, [rbp+60h+var_B8]
0x1800fab6d  lea     r9, [rbp+60h+var_D0]
0x1800fab71  lea     r8, [rbp+60h+var_B0]
0x1800fab75  mov     rcx, rbx
0x1800fab78  call    LdrpAccessResourceDataNoMultipleLanguage
0x1800fab7d  test    eax, eax
0x1800fab7f  js      short loc_1800FAB8F
0x1800fab81  mov     rax, [rbp+60h+var_B0]
0x1800fab85  cmp     dword ptr [rax], 0FECDFECDh
0x1800fab8b  cmovz   edi, r12d
0x1800fab8f  mov     rdx, [rsp+160h+var_100]
0x1800fab94  test    rdx, rdx
0x1800fab97  jz      short loc_1800FABA2
0x1800fab99  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800fab9d  call    NtUnmapViewOfSection
0x1800faba2  test    r14b, r14b
0x1800faba5  jz      short loc_1800FABB1
0x1800faba7  mov     rcx, [rsp+160h+var_E8]; Handle
0x1800fabac  call    NtClose
0x1800fabb1  mov     al, dil
0x1800fabb4  mov     rcx, [rbp+60h+var_30]
0x1800fabb8  xor     rcx, rsp; StackCookie
0x1800fabbb  call    __security_check_cookie
0x1800fabc0  lea     r11, [rsp+160h+var_20]
0x1800fabc8  mov     rbx, [r11+38h]
0x1800fabcc  mov     rsi, [r11+40h]
0x1800fabd0  mov     rsp, r11
0x1800fabd3  pop     r15
0x1800fabd5  pop     r14
0x1800fabd7  pop     r12
0x1800fabd9  pop     rdi
0x1800fabda  pop     rbp
0x1800fabdb  retn
0x1800fabdd  mov     rdx, qword ptr [rbp+60h+var_98]
0x1800fabe1  mov     word ptr [rbp+60h+var_E0], ax
0x1800fabe5  mov     eax, dword ptr [rbp+60h+var_A8+2]
0x1800fabe8  mov     dword ptr [rbp+60h+var_E0+2], eax
0x1800fabeb  movzx   eax, word ptr [rbp+60h+var_A8+6]
0x1800fabef  mov     word ptr [rbp+60h+var_E0+6], ax
0x1800fabf3  mov     rax, qword ptr [rbp+60h+var_A8+8]
0x1800fabf7  mov     qword ptr [rbp+60h+var_E0+8], rax
0x1800fabfb  jmp     loc_1800FA9D1
```
