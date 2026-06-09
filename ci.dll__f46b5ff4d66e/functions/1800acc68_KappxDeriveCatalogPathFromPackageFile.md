# KappxDeriveCatalogPathFromPackageFile

- ea: `0x1800acc68`
- end: `0x1800acdfe`
- name: `KappxDeriveCatalogPathFromPackageFile`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e1968`

## callees

- `0x18000c6ac`
- `0x18000c800`
- `0x18000d52c`
- `0x18000e080`
- `0x18001e120`
- `0x18002c040`
- `0x1800acc68`

## import_xrefs

- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800acd2b`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800acd2b`

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
0x1800acc68  mov     [rsp-28h+arg_0], rbx
0x1800acc6d  mov     [rsp-28h+arg_8], rsi
0x1800acc72  push    rbp
0x1800acc73  push    rdi
0x1800acc74  push    r12
0x1800acc76  push    r14
0x1800acc78  push    r15
0x1800acc7a  mov     rbp, rsp
0x1800acc7d  sub     rsp, 70h
0x1800acc81  xor     eax, eax
0x1800acc83  mov     [rbp+var_40], 0
0x1800acc8b  xorps   xmm0, xmm0
0x1800acc8e  mov     [rbp+arg_18], ax
0x1800acc92  xorps   xmm1, xmm1
0x1800acc95  mov     [rbp+pusResult], ax
0x1800acc99  movups  [rbp+var_18], xmm0
0x1800acc9d  mov     [rbp+var_38], rax
0x1800acca1  mov     rdi, r8
0x1800acca4  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1800acca8  mov     r12, rdx
0x1800accab  mov     [rbp+var_48], 0
0x1800accb3  mov     rbx, rcx
0x1800accb6  mov     [rbp+Src], 0
0x1800accbe  call    KappxpInitializeRepositoryPath
0x1800accc3  test    eax, eax
0x1800accc5  jns     short loc_1800ACCE1
0x1800accc7  lea     r11, [rsp+70h+var_s0]
0x1800acccc  mov     rbx, [r11+30h]
0x1800accd0  mov     rsi, [r11+38h]
0x1800accd4  mov     rsp, r11
0x1800accd7  pop     r15
0x1800accd9  pop     r14
0x1800accdb  pop     r12
0x1800accdd  pop     rdi
0x1800accde  pop     rbp
0x1800accdf  retn
0x1800acce1  lea     r8, [rbp+var_48]
0x1800acce5  mov     rcx, rbx
0x1800acce8  lea     rdx, [rbp+var_18]
0x1800accec  call    KappxpGetFileNameInformation
0x1800accf1  test    eax, eax
0x1800accf3  js      short loc_1800ACCC7
0x1800accf5  mov     rcx, [rbp+var_48]
0x1800accf9  lea     r8, [rbp+var_40]
0x1800accfd  lea     rdx, [rbp+String2]
0x1800acd01  call    KappxpDeriveVolumeRelativePathFromFileNameInformation
0x1800acd06  mov     ebx, eax
0x1800acd08  test    eax, eax
0x1800acd0a  js      short loc_1800ACD27
0x1800acd0c  lea     r9, [rbp+var_38]
0x1800acd10  lea     r8, [rbp+arg_18]
0x1800acd14  lea     rdx, [rbp+Src]
0x1800acd18  lea     rcx, [rbp+String2]; String2
0x1800acd1c  call    KappxpParsePackageFile
0x1800acd21  mov     ebx, eax
0x1800acd23  test    eax, eax
0x1800acd25  jns     short loc_1800ACD3B
0x1800acd27  mov     rcx, [rbp+var_48]
0x1800acd2b  call    cs:__imp_FsRtlReleaseFileNameInformation
0x1800acd32  nop     dword ptr [rax+rax+00h]
0x1800acd37  mov     eax, ebx
0x1800acd39  jmp     short loc_1800ACCC7
0x1800acd3b  mov     r15, [rbp+var_40]
0x1800acd3f  lea     r8, [rbp+pusResult]; pusResult
0x1800acd43  mov     r14, [rbp+var_38]
0x1800acd47  mov     edx, 40h ; '@'; usAddend
0x1800acd4c  movzx   r9d, word ptr [r15]
0x1800acd50  movzx   ecx, r9w
0x1800acd54  add     cx, [r14]
0x1800acd58  add     cx, [rbp+arg_18]; usAugend
0x1800acd5c  call    RtlUShortAdd
0x1800acd61  mov     ebx, eax
0x1800acd63  test    eax, eax
0x1800acd65  js      short loc_1800ACD27
0x1800acd67  movzx   esi, [rbp+pusResult]
0x1800acd6b  mov     rax, [rdi]
0x1800acd6e  mov     [rdi], rsi
0x1800acd71  cmp     rsi, rax
0x1800acd74  jbe     short loc_1800ACD7D
0x1800acd76  mov     ebx, 0C0000023h
0x1800acd7b  jmp     short loc_1800ACD27
0x1800acd7d  mov     rdx, [r15+8]; Src
0x1800acd81  mov     r8, r9; Size
0x1800acd84  mov     rcx, r12; void *
0x1800acd87  call    memmove
0x1800acd8c  movzx   ebx, word ptr [r15]
0x1800acd90  movzx   r8d, word ptr [r14]; Size
0x1800acd94  add     rbx, r12
0x1800acd97  mov     rdx, [r14+8]; Src
0x1800acd9b  mov     rcx, rbx; void *
0x1800acd9e  call    memmove
0x1800acda3  movzx   edi, word ptr [r14]
0x1800acda7  mov     rdx, [rbp+Src]; Src
0x1800acdab  add     rdi, rbx
0x1800acdae  movzx   ebx, [rbp+arg_18]
0x1800acdb2  mov     rcx, rdi; void *
0x1800acdb5  mov     r8d, ebx; Size
0x1800acdb8  call    memmove
0x1800acdbd  movaps  xmm0, xmmword ptr cs:aAppxmetadataCo; "\\AppxMetadata\\CodeIntegrity.cat"
0x1800acdc4  xor     eax, eax
0x1800acdc6  movups  xmmword ptr [rbx+rdi], xmm0
0x1800acdca  shr     rsi, 1
0x1800acdcd  movaps  xmm1, xmmword ptr cs:aAppxmetadataCo+10h; "adata\\CodeIntegrity.cat"
0x1800acdd4  movups  xmmword ptr [rbx+rdi+10h], xmm1
0x1800acdd9  movaps  xmm0, xmmword ptr cs:aAppxmetadataCo+20h; "deIntegrity.cat"
0x1800acde0  movups  xmmword ptr [rbx+rdi+20h], xmm0
0x1800acde5  movups  xmm1, xmmword ptr cs:aAppxmetadataCo+2Eh; "rity.cat"
0x1800acdec  movups  xmmword ptr [rbx+rdi+2Eh], xmm1
0x1800acdf1  mov     [r12+rsi*2-2], ax
0x1800acdf7  xor     ebx, ebx
0x1800acdf9  jmp     loc_1800ACD27
```
