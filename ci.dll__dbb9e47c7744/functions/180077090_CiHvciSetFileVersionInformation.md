# CiHvciSetFileVersionInformation

- ea: `0x180077090`
- end: `0x1800772e1`
- name: `CiHvciSetFileVersionInformation`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x18000eda0`
- `0x18002c000`
- `0x18005a398`
- `0x180076420`
- `0x180077090`
- `0x18009b020`

## import_xrefs

- `ntoskrnl!LdrResFindResource` at `0x180077238`
- `ntoskrnl!LdrResFindResource` at `0x180077238`

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
        FileOffsetForRva = ((__int64 (__fastcall *)(_QWORD, __int64, char *, _QWORD, __int64))xmmword_18004A640)(
                             *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
                             1,
                             &a3[v10],
                             v14,
                             v12);
      if ( FileOffsetForRva >= 0 )
      {
        FileOffsetForRva = CiGetFileOffsetForRva(v17, v11, &v12);
        if ( FileOffsetForRva >= 0 )
        {
          FileOffsetForRva = ((__int64 (__fastcall *)(_QWORD, __int64, char *, _QWORD, __int64))xmmword_18004A640)(
                               *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
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
                  return (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _QWORD *, _QWORD, _QWORD, _DWORD))xmmword_18004A640)(
                                         *(_QWORD *)(*(_QWORD *)(a1 + 3056) + 16LL),
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
0x180077090  mov     rax, rsp
0x180077093  push    rbx
0x180077094  push    rsi
0x180077095  push    rdi
0x180077096  push    r14
0x180077098  sub     rsp, 98h
0x18007709f  mov     edi, r9d
0x1800770a2  mov     rbx, r8
0x1800770a5  mov     rsi, rcx
0x1800770a8  xor     r14d, r14d
0x1800770ab  mov     [rax-60h], r14
0x1800770af  mov     [rax-48h], r14
0x1800770b3  mov     [rax-58h], r14d
0x1800770b7  mov     [rax-40h], r14
0x1800770bb  mov     [rax-38h], r14
0x1800770bf  mov     [rax-64h], r14d
0x1800770c3  mov     [rax-50h], r14d
0x1800770c7  mov     [rax-68h], r14d
0x1800770cb  mov     [rax-54h], r14d
0x1800770cf  call    CipSetFileVersionInformation
0x1800770d4  mov     ecx, eax
0x1800770d6  test    eax, eax
0x1800770d8  js      loc_1800772D1
0x1800770de  lea     r9, [rsp+0B8h+var_58]
0x1800770e3  lea     r8, [rsp+0B8h+var_48]
0x1800770e8  mov     edx, edi; Size
0x1800770ea  mov     rcx, rbx; BaseAddress
0x1800770ed  call    CiValidateImageHeaderMapping
0x1800770f2  mov     ecx, eax
0x1800770f4  test    eax, eax
0x1800770f6  js      loc_1800772D1
0x1800770fc  test    cs:g_CiPolicyState, 400000h
0x180077106  jz      loc_180077204
0x18007710c  lea     rax, [rsp+0B8h+var_50]
0x180077111  mov     [rsp+0B8h+var_78], rax
0x180077116  lea     rax, [rsp+0B8h+var_64]
0x18007711b  mov     [rsp+0B8h+var_80], rax
0x180077120  lea     rax, [rsp+0B8h+var_54]
0x180077125  mov     [rsp+0B8h+var_88], rax
0x18007712a  lea     rax, [rsp+0B8h+var_68]
0x18007712f  mov     [rsp+0B8h+var_90], rax
0x180077134  mov     [rsp+0B8h+var_98], r14
0x180077139  mov     r9d, edi
0x18007713c  mov     r8, rbx
0x18007713f  mov     edx, [rsp+0B8h+var_58]
0x180077143  mov     rcx, [rsp+0B8h+var_48]
0x180077148  call    CiGetHotpatchSequenceNumberAndRegionsFromImage
0x18007714d  test    eax, eax
0x18007714f  js      loc_180077204
0x180077155  lea     r8, [rsp+0B8h+var_60]
0x18007715a  mov     edx, [rsp+0B8h+var_68]
0x18007715e  mov     rcx, [rsp+0B8h+var_48]
0x180077163  call    CiGetFileOffsetForRva
0x180077168  mov     ecx, eax
0x18007716a  test    eax, eax
0x18007716c  js      short loc_1800771A2
0x18007716e  mov     r9d, [rsp+0B8h+var_54]
0x180077173  mov     r8d, [rsp+0B8h+var_68]
0x180077178  add     r8, rbx
0x18007717b  mov     rcx, [rsi+0BF0h]
0x180077182  mov     rax, qword ptr cs:xmmword_18004A640
0x180077189  mov     rdx, [rsp+0B8h+var_60]
0x18007718e  mov     [rsp+0B8h+var_98], rdx
0x180077193  lea     edx, [r14+1]
0x180077197  mov     rcx, [rcx+10h]
0x18007719b  call    _guard_dispatch_icall
0x1800771a0  mov     ecx, eax
0x1800771a2  test    ecx, ecx
0x1800771a4  js      loc_1800772D1
0x1800771aa  lea     r8, [rsp+0B8h+var_60]
0x1800771af  mov     edx, [rsp+0B8h+var_64]
0x1800771b3  mov     rcx, [rsp+0B8h+var_48]
0x1800771b8  call    CiGetFileOffsetForRva
0x1800771bd  mov     ecx, eax
0x1800771bf  test    eax, eax
0x1800771c1  js      loc_1800772D1
0x1800771c7  mov     r9d, [rsp+0B8h+var_50]
0x1800771cc  mov     r8d, [rsp+0B8h+var_64]
0x1800771d1  add     r8, rbx
0x1800771d4  mov     rcx, [rsi+0BF0h]
0x1800771db  mov     rax, qword ptr cs:xmmword_18004A640
0x1800771e2  mov     rdx, [rsp+0B8h+var_60]
0x1800771e7  mov     [rsp+0B8h+var_98], rdx
0x1800771ec  mov     edx, 2
0x1800771f1  mov     rcx, [rcx+10h]
0x1800771f5  call    _guard_dispatch_icall
0x1800771fa  mov     ecx, eax
0x1800771fc  test    eax, eax
0x1800771fe  js      loc_1800772D1
0x180077204  mov     dword ptr [rsp+0B8h+var_78], r14d
0x180077209  mov     [rsp+0B8h+var_80], r14
0x18007720e  mov     [rsp+0B8h+var_88], r14
0x180077213  lea     rax, [rsp+0B8h+var_38]
0x18007721b  mov     [rsp+0B8h+var_90], rax
0x180077220  lea     rax, [rsp+0B8h+var_40]
0x180077225  mov     [rsp+0B8h+var_98], rax
0x18007722a  xor     r9d, r9d
0x18007722d  lea     edx, [r9+10h]
0x180077231  lea     r8d, [r9+1]
0x180077235  mov     rcx, rbx
0x180077238  call    cs:__imp_LdrResFindResource
0x18007723f  nop     dword ptr [rax+rax+00h]
0x180077244  mov     ecx, eax
0x180077246  mov     [rsp+0B8h+var_4C], eax
0x18007724a  test    eax, eax
0x18007724c  jns     short loc_180077269
0x18007724e  add     eax, 3FFFFF77h
0x180077253  cmp     eax, 2
0x180077256  jbe     short loc_180077260
0x180077258  cmp     ecx, 0C0000204h
0x18007725e  jnz     short loc_180077267
0x180077260  mov     ecx, r14d
0x180077263  mov     [rsp+0B8h+var_4C], ecx
0x180077267  jmp     short loc_1800772D1
0x180077269  mov     rdx, [rsp+0B8h+var_40]
0x18007726e  sub     rdx, rbx
0x180077271  mov     eax, 0FFFFFFFFh
0x180077276  cmp     rdx, rax
0x180077279  ja      short loc_1800772C4
0x18007727b  lea     r8, [rsp+0B8h+var_60]
0x180077280  mov     rcx, [rsp+0B8h+var_48]
0x180077285  call    CiGetFileOffsetForRva
0x18007728a  mov     ecx, eax
0x18007728c  test    eax, eax
0x18007728e  js      short loc_1800772D1
0x180077290  mov     rcx, [rsi+0BF0h]
0x180077297  mov     rax, qword ptr cs:xmmword_18004A640
0x18007729e  mov     rdx, [rsp+0B8h+var_60]
0x1800772a3  mov     [rsp+0B8h+var_98], rdx
0x1800772a8  mov     r9, [rsp+0B8h+var_38]
0x1800772b0  mov     r8, [rsp+0B8h+var_40]
0x1800772b5  xor     edx, edx
0x1800772b7  mov     rcx, [rcx+10h]
0x1800772bb  call    _guard_dispatch_icall
0x1800772c0  mov     ecx, eax
0x1800772c2  jmp     short loc_1800772D1
0x1800772c4  mov     ecx, 0C0000095h
0x1800772c9  jmp     short loc_1800772D1
0x1800772cb  mov     ecx, eax
0x1800772cd  mov     [rsp+0B8h+var_4C], eax
0x1800772d1  mov     eax, ecx
0x1800772d3  add     rsp, 98h
0x1800772da  pop     r14
0x1800772dc  pop     rdi
0x1800772dd  pop     rsi
0x1800772de  pop     rbx
0x1800772df  retn
```
