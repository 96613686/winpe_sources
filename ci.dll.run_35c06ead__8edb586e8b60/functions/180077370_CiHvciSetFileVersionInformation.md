# CiHvciSetFileVersionInformation

- ea: `0x180077370`
- end: `0x1800775c1`
- name: `CiHvciSetFileVersionInformation`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x18000edb0`
- `0x18002c1b0`
- `0x18005a2c0`
- `0x180076700`
- `0x180077370`
- `0x1800a0360`

## import_xrefs

- `ntoskrnl!LdrResFindResource` at `0x180077518`
- `ntoskrnl!LdrResFindResource` at `0x180077518`

## pseudocode

```c
__int64 __fastcall CiHvciSetFileVersionInformation(__int64 a1, __int64 a2, char *a3, unsigned int a4)
{
  int FileOffsetForRva; // ecx
  int Resource; // eax
  unsigned int v10; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v11; // [rsp+54h] [rbp-64h] BYREF
  __int64 v12; // [rsp+58h] [rbp-60h] BYREF
  DWORD v13; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v14; // [rsp+64h] [rbp-54h] BYREF
  unsigned int v15; // [rsp+68h] [rbp-50h] BYREF
  int v16; // [rsp+6Ch] [rbp-4Ch]
  __int64 v17; // [rsp+70h] [rbp-48h] BYREF
  __int64 v18; // [rsp+78h] [rbp-40h]
  _QWORD v19[7]; // [rsp+80h] [rbp-38h] BYREF

  v12 = 0;
  v17 = 0;
  v13 = 0;
  v18 = 0;
  v19[0] = 0;
  v11 = 0;
  v15 = 0;
  v10 = 0;
  v14 = 0;
  FileOffsetForRva = CipSetFileVersionInformation();
  if ( FileOffsetForRva >= 0 )
  {
    FileOffsetForRva = CiValidateImageHeaderMapping(a3, a4, &v17, &v13);
    if ( FileOffsetForRva >= 0 )
    {
      if ( (g_CiPolicyState & 0x400000) == 0
        || (int)CiGetHotpatchSequenceNumberAndRegionsFromImage(
                  v17,
                  v13,
                  (_DWORD)a3,
                  a4,
                  0,
                  (__int64)&v10,
                  (__int64)&v14,
                  (__int64)&v11,
                  (__int64)&v15) < 0 )
      {
        goto LABEL_10;
      }
      FileOffsetForRva = CiGetFileOffsetForRva(v17, v10, &v12);
      if ( FileOffsetForRva >= 0 )
        FileOffsetForRva = ((__int64 (__fastcall *)(_QWORD, __int64, char *, _QWORD, __int64))xmmword_18004A5E0)(
                             *(_QWORD *)(*(_QWORD *)(a1 + 3072) + 16LL),
                             1,
                             &a3[v10],
                             v14,
                             v12);
      if ( FileOffsetForRva >= 0 )
      {
        FileOffsetForRva = CiGetFileOffsetForRva(v17, v11, &v12);
        if ( FileOffsetForRva >= 0 )
        {
          FileOffsetForRva = ((__int64 (__fastcall *)(_QWORD, __int64, char *, _QWORD, __int64))xmmword_18004A5E0)(
                               *(_QWORD *)(*(_QWORD *)(a1 + 3072) + 16LL),
                               2,
                               &a3[v11],
                               v15,
                               v12);
          if ( FileOffsetForRva >= 0 )
          {
LABEL_10:
            Resource = LdrResFindResource(a3, 16, 1);
            FileOffsetForRva = Resource;
            v16 = Resource;
            if ( Resource >= 0 )
            {
              if ( (unsigned __int64)(v18 - (_QWORD)a3) > 0xFFFFFFFF )
              {
                return (unsigned int)-1073741675;
              }
              else
              {
                FileOffsetForRva = CiGetFileOffsetForRva(v17, v18 - (_QWORD)a3, &v12);
                if ( FileOffsetForRva >= 0 )
                  return (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _QWORD *, _QWORD, _QWORD, _DWORD))xmmword_18004A5E0)(
                                         *(_QWORD *)(*(_QWORD *)(a1 + 3072) + 16LL),
                                         0,
                                         v18,
                                         v19[0],
                                         v12,
                                         v19,
                                         0,
                                         0,
                                         0);
              }
            }
            else if ( (unsigned int)(Resource + 1073741687) <= 2 || Resource == -1073741308 )
            {
              FileOffsetForRva = 0;
              v16 = 0;
            }
          }
        }
      }
    }
  }
  return (unsigned int)FileOffsetForRva;
}

```

## disassembly

```asm
0x180077370  mov     rax, rsp
0x180077373  push    rbx
0x180077374  push    rsi
0x180077375  push    rdi
0x180077376  push    r14
0x180077378  sub     rsp, 98h
0x18007737f  mov     edi, r9d
0x180077382  mov     rbx, r8
0x180077385  mov     rsi, rcx
0x180077388  xor     r14d, r14d
0x18007738b  mov     [rax-60h], r14
0x18007738f  mov     [rax-48h], r14
0x180077393  mov     [rax-58h], r14d
0x180077397  mov     [rax-40h], r14
0x18007739b  mov     [rax-38h], r14
0x18007739f  mov     [rax-64h], r14d
0x1800773a3  mov     [rax-50h], r14d
0x1800773a7  mov     [rax-68h], r14d
0x1800773ab  mov     [rax-54h], r14d
0x1800773af  call    CipSetFileVersionInformation
0x1800773b4  mov     ecx, eax
0x1800773b6  test    eax, eax
0x1800773b8  js      loc_1800775B1
0x1800773be  lea     r9, [rsp+0B8h+var_58]
0x1800773c3  lea     r8, [rsp+0B8h+var_48]
0x1800773c8  mov     edx, edi; Size
0x1800773ca  mov     rcx, rbx; BaseAddress
0x1800773cd  call    CiValidateImageHeaderMapping
0x1800773d2  mov     ecx, eax
0x1800773d4  test    eax, eax
0x1800773d6  js      loc_1800775B1
0x1800773dc  test    cs:g_CiPolicyState, 400000h
0x1800773e6  jz      loc_1800774E4
0x1800773ec  lea     rax, [rsp+0B8h+var_50]
0x1800773f1  mov     [rsp+0B8h+var_78], rax
0x1800773f6  lea     rax, [rsp+0B8h+var_64]
0x1800773fb  mov     [rsp+0B8h+var_80], rax
0x180077400  lea     rax, [rsp+0B8h+var_54]
0x180077405  mov     [rsp+0B8h+var_88], rax
0x18007740a  lea     rax, [rsp+0B8h+var_68]
0x18007740f  mov     [rsp+0B8h+var_90], rax
0x180077414  mov     [rsp+0B8h+var_98], r14
0x180077419  mov     r9d, edi
0x18007741c  mov     r8, rbx
0x18007741f  mov     edx, [rsp+0B8h+var_58]
0x180077423  mov     rcx, [rsp+0B8h+var_48]
0x180077428  call    CiGetHotpatchSequenceNumberAndRegionsFromImage
0x18007742d  test    eax, eax
0x18007742f  js      loc_1800774E4
0x180077435  lea     r8, [rsp+0B8h+var_60]
0x18007743a  mov     edx, [rsp+0B8h+var_68]
0x18007743e  mov     rcx, [rsp+0B8h+var_48]
0x180077443  call    CiGetFileOffsetForRva
0x180077448  mov     ecx, eax
0x18007744a  test    eax, eax
0x18007744c  js      short loc_180077482
0x18007744e  mov     r9d, [rsp+0B8h+var_54]
0x180077453  mov     r8d, [rsp+0B8h+var_68]
0x180077458  add     r8, rbx
0x18007745b  mov     rcx, [rsi+0C00h]
0x180077462  mov     rax, qword ptr cs:xmmword_18004A5E0
0x180077469  mov     rdx, [rsp+0B8h+var_60]
0x18007746e  mov     [rsp+0B8h+var_98], rdx
0x180077473  lea     edx, [r14+1]
0x180077477  mov     rcx, [rcx+10h]
0x18007747b  call    _guard_dispatch_icall
0x180077480  mov     ecx, eax
0x180077482  test    ecx, ecx
0x180077484  js      loc_1800775B1
0x18007748a  lea     r8, [rsp+0B8h+var_60]
0x18007748f  mov     edx, [rsp+0B8h+var_64]
0x180077493  mov     rcx, [rsp+0B8h+var_48]
0x180077498  call    CiGetFileOffsetForRva
0x18007749d  mov     ecx, eax
0x18007749f  test    eax, eax
0x1800774a1  js      loc_1800775B1
0x1800774a7  mov     r9d, [rsp+0B8h+var_50]
0x1800774ac  mov     r8d, [rsp+0B8h+var_64]
0x1800774b1  add     r8, rbx
0x1800774b4  mov     rcx, [rsi+0C00h]
0x1800774bb  mov     rax, qword ptr cs:xmmword_18004A5E0
0x1800774c2  mov     rdx, [rsp+0B8h+var_60]
0x1800774c7  mov     [rsp+0B8h+var_98], rdx
0x1800774cc  mov     edx, 2
0x1800774d1  mov     rcx, [rcx+10h]
0x1800774d5  call    _guard_dispatch_icall
0x1800774da  mov     ecx, eax
0x1800774dc  test    eax, eax
0x1800774de  js      loc_1800775B1
0x1800774e4  mov     dword ptr [rsp+0B8h+var_78], r14d
0x1800774e9  mov     [rsp+0B8h+var_80], r14
0x1800774ee  mov     [rsp+0B8h+var_88], r14
0x1800774f3  lea     rax, [rsp+0B8h+var_38]
0x1800774fb  mov     [rsp+0B8h+var_90], rax
0x180077500  lea     rax, [rsp+0B8h+var_40]
0x180077505  mov     [rsp+0B8h+var_98], rax
0x18007750a  xor     r9d, r9d
0x18007750d  lea     edx, [r9+10h]
0x180077511  lea     r8d, [r9+1]
0x180077515  mov     rcx, rbx
0x180077518  call    cs:__imp_LdrResFindResource
0x18007751f  nop     dword ptr [rax+rax+00h]
0x180077524  mov     ecx, eax
0x180077526  mov     [rsp+0B8h+var_4C], eax
0x18007752a  test    eax, eax
0x18007752c  jns     short loc_180077549
0x18007752e  add     eax, 3FFFFF77h
0x180077533  cmp     eax, 2
0x180077536  jbe     short loc_180077540
0x180077538  cmp     ecx, 0C0000204h
0x18007753e  jnz     short loc_180077547
0x180077540  mov     ecx, r14d
0x180077543  mov     [rsp+0B8h+var_4C], ecx
0x180077547  jmp     short loc_1800775B1
0x180077549  mov     rdx, [rsp+0B8h+var_40]
0x18007754e  sub     rdx, rbx
0x180077551  mov     eax, 0FFFFFFFFh
0x180077556  cmp     rdx, rax
0x180077559  ja      short loc_1800775A4
0x18007755b  lea     r8, [rsp+0B8h+var_60]
0x180077560  mov     rcx, [rsp+0B8h+var_48]
0x180077565  call    CiGetFileOffsetForRva
0x18007756a  mov     ecx, eax
0x18007756c  test    eax, eax
0x18007756e  js      short loc_1800775B1
0x180077570  mov     rcx, [rsi+0C00h]
0x180077577  mov     rax, qword ptr cs:xmmword_18004A5E0
0x18007757e  mov     rdx, [rsp+0B8h+var_60]
0x180077583  mov     [rsp+0B8h+var_98], rdx
0x180077588  mov     r9, [rsp+0B8h+var_38]
0x180077590  mov     r8, [rsp+0B8h+var_40]
0x180077595  xor     edx, edx
0x180077597  mov     rcx, [rcx+10h]
0x18007759b  call    _guard_dispatch_icall
0x1800775a0  mov     ecx, eax
0x1800775a2  jmp     short loc_1800775B1
0x1800775a4  mov     ecx, 0C0000095h
0x1800775a9  jmp     short loc_1800775B1
0x1800775ab  mov     ecx, eax
0x1800775ad  mov     [rsp+0B8h+var_4C], eax
0x1800775b1  mov     eax, ecx
0x1800775b3  add     rsp, 98h
0x1800775ba  pop     r14
0x1800775bc  pop     rdi
0x1800775bd  pop     rsi
0x1800775be  pop     rbx
0x1800775bf  retn
```
