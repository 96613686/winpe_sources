# KappxDeriveCatalogPathFromPackageFile

- ea: `0x1800ae0e8`
- end: `0x1800ae27e`
- name: `KappxDeriveCatalogPathFromPackageFile`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e2958`

## callees

- `0x18000c6ac`
- `0x18000c800`
- `0x18000d52c`
- `0x18000e080`
- `0x18001e064`
- `0x18002c080`
- `0x1800ae0e8`

## import_xrefs

- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800ae1ab`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800ae1ab`

## pseudocode

```c
__int64 __fastcall KappxDeriveCatalogPathFromPackageFile(__int64 a1, char *a2, unsigned __int64 *a3)
{
  __int64 result; // rax
  NTSTATUS v7; // ebx
  const void **v8; // r15
  const void **v9; // r14
  size_t v10; // r9
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rax
  char *v13; // rbx
  char *v14; // rdi
  USHORT pusResult; // [rsp+20h] [rbp-50h] BYREF
  __int64 v16; // [rsp+28h] [rbp-48h] BYREF
  const void **v17; // [rsp+30h] [rbp-40h] BYREF
  const void **v18; // [rsp+38h] [rbp-38h]
  void *Src; // [rsp+40h] [rbp-30h]
  UNICODE_STRING String2; // [rsp+48h] [rbp-28h] BYREF
  __int128 v21; // [rsp+58h] [rbp-18h] BYREF

  v17 = 0;
  pusResult = 0;
  v21 = 0;
  v18 = 0;
  String2 = 0;
  v16 = 0;
  Src = 0;
  result = KappxpInitializeRepositoryPath();
  if ( (int)result >= 0 )
  {
    result = KappxpGetFileNameInformation(a1, &v21, &v16);
    if ( (int)result >= 0 )
    {
      v7 = KappxpDeriveVolumeRelativePathFromFileNameInformation(v16, &String2, &v17);
      if ( v7 >= 0 )
      {
        v7 = KappxpParsePackageFile(&String2);
        if ( v7 >= 0 )
        {
          v8 = v17;
          v9 = v18;
          v7 = RtlUShortAdd(*(_WORD *)v18 + *(_WORD *)v17, 0x40u, &pusResult);
          if ( v7 >= 0 )
          {
            v11 = pusResult;
            v12 = *a3;
            *a3 = pusResult;
            if ( v11 <= v12 )
            {
              memmove(a2, v8[1], v10);
              v13 = &a2[*(unsigned __int16 *)v8];
              memmove(v13, v9[1], *(unsigned __int16 *)v9);
              v14 = &v13[*(unsigned __int16 *)v9];
              memmove(v14, Src, 0);
              *(_OWORD *)v14 = *(_OWORD *)L"\\AppxMetadata\\CodeIntegrity.cat";
              *((_OWORD *)v14 + 1) = *(_OWORD *)L"adata\\CodeIntegrity.cat";
              *((_OWORD *)v14 + 2) = *(_OWORD *)L"deIntegrity.cat";
              *(_OWORD *)(v14 + 46) = *(_OWORD *)L"rity.cat";
              *(_WORD *)&a2[2 * (v11 >> 1) - 2] = 0;
              v7 = 0;
            }
            else
            {
              v7 = -1073741789;
            }
          }
        }
      }
      FsRtlReleaseFileNameInformation(v16);
      return (unsigned int)v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ae0e8  mov     [rsp-28h+arg_0], rbx
0x1800ae0ed  mov     [rsp-28h+arg_8], rsi
0x1800ae0f2  push    rbp
0x1800ae0f3  push    rdi
0x1800ae0f4  push    r12
0x1800ae0f6  push    r14
0x1800ae0f8  push    r15
0x1800ae0fa  mov     rbp, rsp
0x1800ae0fd  sub     rsp, 70h
0x1800ae101  xor     eax, eax
0x1800ae103  mov     [rbp+var_40], 0
0x1800ae10b  xorps   xmm0, xmm0
0x1800ae10e  mov     [rbp+arg_18], ax
0x1800ae112  xorps   xmm1, xmm1
0x1800ae115  mov     [rbp+pusResult], ax
0x1800ae119  movups  [rbp+var_18], xmm0
0x1800ae11d  mov     [rbp+var_38], rax
0x1800ae121  mov     rdi, r8
0x1800ae124  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1800ae128  mov     r12, rdx
0x1800ae12b  mov     [rbp+var_48], 0
0x1800ae133  mov     rbx, rcx
0x1800ae136  mov     [rbp+Src], 0
0x1800ae13e  call    KappxpInitializeRepositoryPath
0x1800ae143  test    eax, eax
0x1800ae145  jns     short loc_1800AE161
0x1800ae147  lea     r11, [rsp+70h+var_s0]
0x1800ae14c  mov     rbx, [r11+30h]
0x1800ae150  mov     rsi, [r11+38h]
0x1800ae154  mov     rsp, r11
0x1800ae157  pop     r15
0x1800ae159  pop     r14
0x1800ae15b  pop     r12
0x1800ae15d  pop     rdi
0x1800ae15e  pop     rbp
0x1800ae15f  retn
0x1800ae161  lea     r8, [rbp+var_48]
0x1800ae165  mov     rcx, rbx
0x1800ae168  lea     rdx, [rbp+var_18]
0x1800ae16c  call    KappxpGetFileNameInformation
0x1800ae171  test    eax, eax
0x1800ae173  js      short loc_1800AE147
0x1800ae175  mov     rcx, [rbp+var_48]
0x1800ae179  lea     r8, [rbp+var_40]
0x1800ae17d  lea     rdx, [rbp+String2]
0x1800ae181  call    KappxpDeriveVolumeRelativePathFromFileNameInformation
0x1800ae186  mov     ebx, eax
0x1800ae188  test    eax, eax
0x1800ae18a  js      short loc_1800AE1A7
0x1800ae18c  lea     r9, [rbp+var_38]
0x1800ae190  lea     r8, [rbp+arg_18]
0x1800ae194  lea     rdx, [rbp+Src]
0x1800ae198  lea     rcx, [rbp+String2]; String2
0x1800ae19c  call    KappxpParsePackageFile
0x1800ae1a1  mov     ebx, eax
0x1800ae1a3  test    eax, eax
0x1800ae1a5  jns     short loc_1800AE1BB
0x1800ae1a7  mov     rcx, [rbp+var_48]
0x1800ae1ab  call    cs:__imp_FsRtlReleaseFileNameInformation
0x1800ae1b2  nop     dword ptr [rax+rax+00h]
0x1800ae1b7  mov     eax, ebx
0x1800ae1b9  jmp     short loc_1800AE147
0x1800ae1bb  mov     r15, [rbp+var_40]
0x1800ae1bf  lea     r8, [rbp+pusResult]; pusResult
0x1800ae1c3  mov     r14, [rbp+var_38]
0x1800ae1c7  mov     edx, 40h ; '@'; usAddend
0x1800ae1cc  movzx   r9d, word ptr [r15]
0x1800ae1d0  movzx   ecx, r9w
0x1800ae1d4  add     cx, [r14]
0x1800ae1d8  add     cx, [rbp+arg_18]; usAugend
0x1800ae1dc  call    RtlUShortAdd
0x1800ae1e1  mov     ebx, eax
0x1800ae1e3  test    eax, eax
0x1800ae1e5  js      short loc_1800AE1A7
0x1800ae1e7  movzx   esi, [rbp+pusResult]
0x1800ae1eb  mov     rax, [rdi]
0x1800ae1ee  mov     [rdi], rsi
0x1800ae1f1  cmp     rsi, rax
0x1800ae1f4  jbe     short loc_1800AE1FD
0x1800ae1f6  mov     ebx, 0C0000023h
0x1800ae1fb  jmp     short loc_1800AE1A7
0x1800ae1fd  mov     rdx, [r15+8]; Src
0x1800ae201  mov     r8, r9; Size
0x1800ae204  mov     rcx, r12; void *
0x1800ae207  call    memmove
0x1800ae20c  movzx   ebx, word ptr [r15]
0x1800ae210  movzx   r8d, word ptr [r14]; Size
0x1800ae214  add     rbx, r12
0x1800ae217  mov     rdx, [r14+8]; Src
0x1800ae21b  mov     rcx, rbx; void *
0x1800ae21e  call    memmove
0x1800ae223  movzx   edi, word ptr [r14]
0x1800ae227  mov     rdx, [rbp+Src]; Src
0x1800ae22b  add     rdi, rbx
0x1800ae22e  movzx   ebx, [rbp+arg_18]
0x1800ae232  mov     rcx, rdi; void *
0x1800ae235  mov     r8d, ebx; Size
0x1800ae238  call    memmove
0x1800ae23d  movaps  xmm0, xmmword ptr cs:aAppxmetadataCo; "\\AppxMetadata\\CodeIntegrity.cat"
0x1800ae244  xor     eax, eax
0x1800ae246  movups  xmmword ptr [rbx+rdi], xmm0
0x1800ae24a  shr     rsi, 1
0x1800ae24d  movaps  xmm1, xmmword ptr cs:aAppxmetadataCo+10h; "adata\\CodeIntegrity.cat"
0x1800ae254  movups  xmmword ptr [rbx+rdi+10h], xmm1
0x1800ae259  movaps  xmm0, xmmword ptr cs:aAppxmetadataCo+20h; "deIntegrity.cat"
0x1800ae260  movups  xmmword ptr [rbx+rdi+20h], xmm0
0x1800ae265  movups  xmm1, xmmword ptr cs:aAppxmetadataCo+2Eh; "rity.cat"
0x1800ae26c  movups  xmmword ptr [rbx+rdi+2Eh], xmm1
0x1800ae271  mov     [r12+rsi*2-2], ax
0x1800ae277  xor     ebx, ebx
0x1800ae279  jmp     loc_1800AE1A7
```
