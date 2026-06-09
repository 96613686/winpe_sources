# KappxDeriveCatalogPathFromPackageFile

- ea: `0x1800adf88`
- end: `0x1800ae11e`
- name: `KappxDeriveCatalogPathFromPackageFile`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e2868`

## callees

- `0x18000c6bc`
- `0x18000c810`
- `0x18000d53c`
- `0x18000e090`
- `0x18001e138`
- `0x18002c200`
- `0x1800adf88`

## import_xrefs

- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800ae04b`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800ae04b`

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
0x1800adf88  mov     [rsp-28h+arg_0], rbx
0x1800adf8d  mov     [rsp-28h+arg_8], rsi
0x1800adf92  push    rbp
0x1800adf93  push    rdi
0x1800adf94  push    r12
0x1800adf96  push    r14
0x1800adf98  push    r15
0x1800adf9a  mov     rbp, rsp
0x1800adf9d  sub     rsp, 70h
0x1800adfa1  xor     eax, eax
0x1800adfa3  mov     [rbp+var_40], 0
0x1800adfab  xorps   xmm0, xmm0
0x1800adfae  mov     [rbp+arg_18], ax
0x1800adfb2  xorps   xmm1, xmm1
0x1800adfb5  mov     [rbp+pusResult], ax
0x1800adfb9  movups  [rbp+var_18], xmm0
0x1800adfbd  mov     [rbp+var_38], rax
0x1800adfc1  mov     rdi, r8
0x1800adfc4  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1800adfc8  mov     r12, rdx
0x1800adfcb  mov     [rbp+var_48], 0
0x1800adfd3  mov     rbx, rcx
0x1800adfd6  mov     [rbp+Src], 0
0x1800adfde  call    KappxpInitializeRepositoryPath
0x1800adfe3  test    eax, eax
0x1800adfe5  jns     short loc_1800AE001
0x1800adfe7  lea     r11, [rsp+70h+var_s0]
0x1800adfec  mov     rbx, [r11+30h]
0x1800adff0  mov     rsi, [r11+38h]
0x1800adff4  mov     rsp, r11
0x1800adff7  pop     r15
0x1800adff9  pop     r14
0x1800adffb  pop     r12
0x1800adffd  pop     rdi
0x1800adffe  pop     rbp
0x1800adfff  retn
0x1800ae001  lea     r8, [rbp+var_48]
0x1800ae005  mov     rcx, rbx
0x1800ae008  lea     rdx, [rbp+var_18]
0x1800ae00c  call    KappxpGetFileNameInformation
0x1800ae011  test    eax, eax
0x1800ae013  js      short loc_1800ADFE7
0x1800ae015  mov     rcx, [rbp+var_48]
0x1800ae019  lea     r8, [rbp+var_40]
0x1800ae01d  lea     rdx, [rbp+String2]
0x1800ae021  call    KappxpDeriveVolumeRelativePathFromFileNameInformation
0x1800ae026  mov     ebx, eax
0x1800ae028  test    eax, eax
0x1800ae02a  js      short loc_1800AE047
0x1800ae02c  lea     r9, [rbp+var_38]
0x1800ae030  lea     r8, [rbp+arg_18]
0x1800ae034  lea     rdx, [rbp+Src]
0x1800ae038  lea     rcx, [rbp+String2]; String2
0x1800ae03c  call    KappxpParsePackageFile
0x1800ae041  mov     ebx, eax
0x1800ae043  test    eax, eax
0x1800ae045  jns     short loc_1800AE05B
0x1800ae047  mov     rcx, [rbp+var_48]
0x1800ae04b  call    cs:__imp_FsRtlReleaseFileNameInformation
0x1800ae052  nop     dword ptr [rax+rax+00h]
0x1800ae057  mov     eax, ebx
0x1800ae059  jmp     short loc_1800ADFE7
0x1800ae05b  mov     r15, [rbp+var_40]
0x1800ae05f  lea     r8, [rbp+pusResult]; pusResult
0x1800ae063  mov     r14, [rbp+var_38]
0x1800ae067  mov     edx, 40h ; '@'; usAddend
0x1800ae06c  movzx   r9d, word ptr [r15]
0x1800ae070  movzx   ecx, r9w
0x1800ae074  add     cx, [r14]
0x1800ae078  add     cx, [rbp+arg_18]; usAugend
0x1800ae07c  call    RtlUShortAdd
0x1800ae081  mov     ebx, eax
0x1800ae083  test    eax, eax
0x1800ae085  js      short loc_1800AE047
0x1800ae087  movzx   esi, [rbp+pusResult]
0x1800ae08b  mov     rax, [rdi]
0x1800ae08e  mov     [rdi], rsi
0x1800ae091  cmp     rsi, rax
0x1800ae094  jbe     short loc_1800AE09D
0x1800ae096  mov     ebx, 0C0000023h
0x1800ae09b  jmp     short loc_1800AE047
0x1800ae09d  mov     rdx, [r15+8]; Src
0x1800ae0a1  mov     r8, r9; Size
0x1800ae0a4  mov     rcx, r12; void *
0x1800ae0a7  call    memmove
0x1800ae0ac  movzx   ebx, word ptr [r15]
0x1800ae0b0  movzx   r8d, word ptr [r14]; Size
0x1800ae0b4  add     rbx, r12
0x1800ae0b7  mov     rdx, [r14+8]; Src
0x1800ae0bb  mov     rcx, rbx; void *
0x1800ae0be  call    memmove
0x1800ae0c3  movzx   edi, word ptr [r14]
0x1800ae0c7  mov     rdx, [rbp+Src]; Src
0x1800ae0cb  add     rdi, rbx
0x1800ae0ce  movzx   ebx, [rbp+arg_18]
0x1800ae0d2  mov     rcx, rdi; void *
0x1800ae0d5  mov     r8d, ebx; Size
0x1800ae0d8  call    memmove
0x1800ae0dd  movaps  xmm0, xmmword ptr cs:aAppxmetadataCo; "\\AppxMetadata\\CodeIntegrity.cat"
0x1800ae0e4  xor     eax, eax
0x1800ae0e6  movups  xmmword ptr [rbx+rdi], xmm0
0x1800ae0ea  shr     rsi, 1
0x1800ae0ed  movaps  xmm1, xmmword ptr cs:aAppxmetadataCo+10h; "adata\\CodeIntegrity.cat"
0x1800ae0f4  movups  xmmword ptr [rbx+rdi+10h], xmm1
0x1800ae0f9  movaps  xmm0, xmmword ptr cs:aAppxmetadataCo+20h; "deIntegrity.cat"
0x1800ae100  movups  xmmword ptr [rbx+rdi+20h], xmm0
0x1800ae105  movups  xmm1, xmmword ptr cs:aAppxmetadataCo+2Eh; "rity.cat"
0x1800ae10c  movups  xmmword ptr [rbx+rdi+2Eh], xmm1
0x1800ae111  mov     [r12+rsi*2-2], ax
0x1800ae117  xor     ebx, ebx
0x1800ae119  jmp     loc_1800AE047
```
