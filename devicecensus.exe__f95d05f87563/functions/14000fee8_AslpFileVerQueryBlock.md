# AslpFileVerQueryBlock

- ea: `0x14000fee8`
- end: `0x140010100`
- name: `AslpFileVerQueryBlock`
- size: `536`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 **, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000f3a8`
- `0x14000fb14`

## callees

- `0x140001e94`
- `0x140007074`
- `0x1400097d4`
- `0x14000fd8c`
- `0x14000fe54`
- `0x14000fee8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400100e0`
- `ntdll!RtlFreeHeap` at `0x1400100e0`

## pseudocode

```c
__int64 __fastcall AslpFileVerQueryBlock(unsigned __int16 *a1, __int64 a2, unsigned __int16 **a3, _QWORD *a4)
{
  unsigned __int16 *v6; // rdi
  const char *v7; // r9
  __int64 v8; // r8
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdx
  _WORD *v12; // rcx
  char *v13; // rsi
  __int16 v14; // bp
  const wchar_t *v15; // r14
  unsigned int v16; // ecx
  unsigned __int16 v17; // r11
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rax
  unsigned __int16 *v20; // rbx
  __int64 v21; // rdx
  _WORD *v23[9]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v24; // [rsp+80h] [rbp+8h] BYREF
  PVOID P; // [rsp+98h] [rbp+20h] BYREF

  v6 = a1;
  P = 0;
  v23[0] = 0;
  v24 = 0;
  *a4 = 0;
  if ( a1[2] )
  {
    v7 = "Version block invalid";
    v8 = 2787;
LABEL_3:
    v9 = -1073741811;
    AslLogCallPrintf(1, "AslpFileVerQueryBlock", v8, v7);
    goto LABEL_27;
  }
  v10 = AslStringDuplicate(&P, a2);
  v9 = v10;
  if ( v10 >= 0 )
  {
    if ( *v6 > 0x7FFFu )
    {
      v7 = "VersionBlock is too long";
      v8 = 2805;
      goto LABEL_3;
    }
    if ( *v6 < 8u )
    {
      v7 = "VersionBlock not long enough";
      v8 = 2810;
      goto LABEL_3;
    }
    v12 = P;
    v13 = (char *)v6 + *v6;
    v14 = *((_WORD *)v13 - 1);
    *((_WORD *)v13 - 1) = 0;
    v15 = AslpFileStringTokenize(v12, v11, v23);
    if ( v15 )
    {
LABEL_11:
      v16 = (_DWORD)v13 - (_DWORD)v6;
      if ( (unsigned int)((_DWORD)v13 - (_DWORD)v6) >= 8
        && *v6 <= v16
        && (int)AslpFileVerBlockGetValueOffset(&v24, (__int64)v6, v16) >= 0 )
      {
        v18 = ((v6[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + v24;
        v19 = *v6;
        v24 = v18;
        if ( v18 <= v19 )
        {
          v20 = (unsigned __int16 *)((char *)v6 + v19);
          v6 = (unsigned __int16 *)((char *)v6 + v18);
          if ( v6 < v20 )
          {
            while ( *v6 > v17 && *v6 <= (unsigned __int64)((char *)v20 - (char *)v6) )
            {
              if ( !wcsicmp_0(v15, v6 + 3) )
              {
                v15 = AslpFileStringTokenize(0, v21, v23);
                if ( v15 )
                  goto LABEL_11;
                goto LABEL_25;
              }
              v6 = (unsigned __int16 *)((char *)v6 + ((*v6 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
              if ( v6 >= v20 )
                break;
              v17 = 8;
            }
          }
        }
      }
      v9 = -1073741275;
    }
    else
    {
      v20 = (unsigned __int16 *)v13;
LABEL_25:
      *a3 = v6;
      *a4 = (char *)v20 - (char *)v6;
      v9 = 0;
    }
    *((_WORD *)v13 - 1) = v14;
  }
  else
  {
    AslLogCallPrintf(1, "AslpFileVerQueryBlock", 2793, "AslStringDuplicate failed [%x]", v10);
  }
LABEL_27:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return v9;
}

```

## disassembly

```asm
0x14000fee8  mov     rax, rsp
0x14000feeb  mov     [rax+10h], rbx
0x14000feef  push    rbp
0x14000fef0  push    rsi
0x14000fef1  push    rdi
0x14000fef2  push    r12
0x14000fef4  push    r13
0x14000fef6  push    r14
0x14000fef8  push    r15
0x14000fefa  sub     rsp, 40h
0x14000fefe  xor     r13d, r13d
0x14000ff01  mov     r15, r9
0x14000ff04  mov     r12, r8
0x14000ff07  mov     rdi, rcx
0x14000ff0a  mov     [rax+20h], r13
0x14000ff0e  mov     [rax-48h], r13
0x14000ff12  mov     [rax+8], r13
0x14000ff16  mov     [r9], r13
0x14000ff19  cmp     [rcx+4], r13w
0x14000ff1e  jz      short loc_14000FF48
0x14000ff20  lea     r9, aVersionBlockIn_0; "Version block invalid"
0x14000ff27  mov     r8d, 0AE3h
0x14000ff2d  lea     rdx, aAslpfileverque; "AslpFileVerQueryBlock"
0x14000ff34  mov     ecx, 1
0x14000ff39  mov     ebx, 0C000000Dh
0x14000ff3e  call    AslLogCallPrintf
0x14000ff43  jmp     loc_1400100C4
0x14000ff48  lea     rcx, [rsp+78h+P]
0x14000ff50  call    AslStringDuplicate
0x14000ff55  mov     ebx, eax
0x14000ff57  test    eax, eax
0x14000ff59  jns     short loc_14000FF82
0x14000ff5b  lea     r9, aAslstringdupli_1; "AslStringDuplicate failed [%x]"
0x14000ff62  mov     [rsp+78h+var_58], eax
0x14000ff66  mov     r8d, 0AE9h
0x14000ff6c  lea     rdx, aAslpfileverque; "AslpFileVerQueryBlock"
0x14000ff73  mov     ecx, 1
0x14000ff78  call    AslLogCallPrintf
0x14000ff7d  jmp     loc_1400100C4
0x14000ff82  mov     eax, 7FFFh
0x14000ff87  cmp     [rdi], ax
0x14000ff8a  jbe     short loc_14000FF9B
0x14000ff8c  lea     r9, aVersionblockIs; "VersionBlock is too long"
0x14000ff93  mov     r8d, 0AF5h
0x14000ff99  jmp     short loc_14000FF2D
0x14000ff9b  mov     eax, 8
0x14000ffa0  cmp     [rdi], ax
0x14000ffa3  jnb     short loc_14000FFB7
0x14000ffa5  lea     r9, aVersionblockNo; "VersionBlock not long enough"
0x14000ffac  mov     r8d, 0AFAh
0x14000ffb2  jmp     loc_14000FF2D
0x14000ffb7  movzx   esi, word ptr [rdi]
0x14000ffba  lea     r8, [rsp+78h+var_48]
0x14000ffbf  mov     rcx, [rsp+78h+P]
0x14000ffc7  add     rsi, rdi
0x14000ffca  movzx   ebp, word ptr [rsi-2]
0x14000ffce  mov     [rsi-2], r13w
0x14000ffd3  call    AslpFileStringTokenize
0x14000ffd8  mov     r14, rax
0x14000ffdb  test    rax, rax
0x14000ffde  jz      loc_1400100B0
0x14000ffe4  mov     ecx, esi
0x14000ffe6  mov     r11d, 8
0x14000ffec  sub     ecx, edi
0x14000ffee  cmp     ecx, r11d
0x14000fff1  jb      loc_1400100A9
0x14000fff7  movzx   eax, word ptr [rdi]
0x14000fffa  cmp     eax, ecx
0x14000fffc  ja      loc_1400100A9
0x140010002  mov     r8d, ecx
0x140010005  mov     rdx, rdi
0x140010008  lea     rcx, [rsp+78h+arg_0]
0x140010010  call    AslpFileVerBlockGetValueOffset
0x140010015  test    eax, eax
0x140010017  js      loc_1400100A9
0x14001001d  mov     rcx, [rsp+78h+arg_0]
0x140010025  movzx   eax, word ptr [rdi+2]
0x140010029  add     rax, 3
0x14001002d  and     rax, 0FFFFFFFFFFFFFFFCh
0x140010031  add     rcx, rax
0x140010034  movzx   eax, word ptr [rdi]
0x140010037  mov     [rsp+78h+arg_0], rcx
0x14001003f  cmp     rcx, rax
0x140010042  ja      short loc_1400100A9
0x140010044  lea     rbx, [rax+rdi]
0x140010048  add     rdi, rcx
0x14001004b  cmp     rdi, rbx
0x14001004e  jnb     short loc_1400100A9
0x140010050  cmp     [rdi], r11w
0x140010054  jbe     short loc_1400100A9
0x140010056  movzx   eax, word ptr [rdi]
0x140010059  mov     rcx, rbx
0x14001005c  sub     rcx, rdi
0x14001005f  cmp     rax, rcx
0x140010062  ja      short loc_1400100A9
0x140010064  lea     rdx, [rdi+6]; String2
0x140010068  mov     rcx, r14; String1
0x14001006b  call    _wcsicmp_0
0x140010070  test    eax, eax
0x140010072  jz      short loc_14001008F
0x140010074  movzx   eax, word ptr [rdi]
0x140010077  add     rax, 3
0x14001007b  and     rax, 0FFFFFFFFFFFFFFFCh
0x14001007f  add     rdi, rax
0x140010082  cmp     rdi, rbx
0x140010085  jnb     short loc_1400100A9
0x140010087  mov     r11d, 8
0x14001008d  jmp     short loc_140010050
0x14001008f  lea     r8, [rsp+78h+var_48]
0x140010094  xor     ecx, ecx
0x140010096  call    AslpFileStringTokenize
0x14001009b  mov     r14, rax
0x14001009e  test    rax, rax
0x1400100a1  jnz     loc_14000FFE4
0x1400100a7  jmp     short loc_1400100B3
0x1400100a9  mov     ebx, 0C0000225h
0x1400100ae  jmp     short loc_1400100C0
0x1400100b0  mov     rbx, rsi
0x1400100b3  sub     rbx, rdi
0x1400100b6  mov     [r12], rdi
0x1400100ba  mov     [r15], rbx
0x1400100bd  mov     ebx, r13d
0x1400100c0  mov     [rsi-2], bp
0x1400100c4  mov     r8, [rsp+78h+P]; P
0x1400100cc  test    r8, r8
0x1400100cf  jz      short loc_1400100E6
0x1400100d1  mov     rcx, gs:60h
0x1400100da  xor     edx, edx; Flags
0x1400100dc  mov     rcx, [rcx+30h]; HeapHandle
0x1400100e0  call    cs:__imp_RtlFreeHeap
0x1400100e6  mov     eax, ebx
0x1400100e8  mov     rbx, [rsp+78h+arg_8]
0x1400100f0  add     rsp, 40h
0x1400100f4  pop     r15
0x1400100f6  pop     r14
0x1400100f8  pop     r13
0x1400100fa  pop     r12
0x1400100fc  pop     rdi
0x1400100fd  pop     rsi
0x1400100fe  pop     rbp
0x1400100ff  retn
```
