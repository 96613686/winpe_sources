# uf::details::GetPackageVersionFromFullName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180026400`
- end: `0x180026528`
- name: `?GetPackageVersionFromFullName@details@uf@@YA?AUsimple_version@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b2d8`

## callees

- `0x180026400`
- `0x180026530`
- `0x1800265dc`
- `0x18002661c`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180026431`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180026481`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180026431`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageIdFromFullName` at `0x180026481`

## string_xrefs

- `0x18002649f`: `shellcommon\internal\shell\inc\UndockedFlighting\UfPackageInfo.h`
- `0x1800264f9`: `shellcommon\internal\shell\inc\UndockedFlighting\UfPackageInfo.h`
- `0x180026516`: `shellcommon\internal\shell\inc\UndockedFlighting\UfPackageInfo.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_WORD *__fastcall uf::details::GetPackageVersionFromFullName(_WORD *a1, const WCHAR *a2)
{
  const WCHAR *v2; // rbx
  const WCHAR *v4; // rcx
  int v5; // eax
  int v6; // eax
  BYTE *v7; // rcx
  BYTE *buffer[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 bufferLength; // [rsp+58h] [rbp+10h] BYREF

  v2 = a2;
  bufferLength = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const WCHAR **)a2;
  v5 = PackageIdFromFullName(v4, 0, &bufferLength, 0);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 != -2147024774 )
  {
    if ( v5 >= 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UfPackageInfo.h",
        (const char *)0x80070057LL,
        (int)buffer[0]);
LABEL_16:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UfPackageInfo.h",
      (const char *)(unsigned int)v5,
      (int)buffer[0]);
  }
  if ( bufferLength < 0x30 )
    goto LABEL_16;
  std::vector<unsigned char>::vector<unsigned char>(buffer, bufferLength);
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  v6 = PackageIdFromFullName(v2, 0, &bufferLength, buffer[0]);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\UfPackageInfo.h",
      (const char *)(unsigned int)v6,
      (int)buffer[0]);
  v7 = buffer[0];
  *a1 = *((_WORD *)buffer[0] + 7);
  a1[1] = *((_WORD *)v7 + 6);
  a1[2] = *((_WORD *)v7 + 5);
  a1[3] = *((_WORD *)v7 + 4);
  std::vector<unsigned char>::_Tidy(buffer);
  return a1;
}

```

## disassembly

```asm
0x180026400  mov     [rsp+arg_0], rbx
0x180026405  push    rdi
0x180026406  sub     rsp, 40h
0x18002640a  mov     rbx, rdx
0x18002640d  mov     rdi, rcx
0x180026410  mov     [rsp+48h+bufferLength], 0
0x180026418  cmp     qword ptr [rdx+18h], 7
0x18002641d  jbe     short loc_180026424
0x18002641f  mov     rcx, [rdx]
0x180026422  jmp     short loc_180026427
0x180026424  mov     rcx, rbx; packageFullName
0x180026427  xor     r9d, r9d; buffer
0x18002642a  lea     r8, [rsp+48h+bufferLength]; bufferLength
0x18002642f  xor     edx, edx; flags
0x180026431  call    cs:__imp_PackageIdFromFullName
0x180026437  test    eax, eax
0x180026439  jle     short loc_180026443
0x18002643b  movzx   eax, ax
0x18002643e  or      eax, 80070000h
0x180026443  cmp     eax, 8007007Ah
0x180026448  jnz     loc_1800264ED
0x18002644e  cmp     [rsp+48h+bufferLength], 30h ; '0'
0x180026453  jb      loc_1800264F1
0x180026459  mov     edx, [rsp+48h+bufferLength]
0x18002645d  lea     rcx, [rsp+48h+buffer]
0x180026462  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180026467  nop
0x180026468  cmp     qword ptr [rbx+18h], 7
0x18002646d  jbe     short loc_180026472
0x18002646f  mov     rbx, [rbx]
0x180026472  mov     r9, [rsp+48h+buffer]; buffer
0x180026477  lea     r8, [rsp+48h+bufferLength]; bufferLength
0x18002647c  xor     edx, edx; flags
0x18002647e  mov     rcx, rbx; packageFullName
0x180026481  call    cs:__imp_PackageIdFromFullName
0x180026487  test    eax, eax
0x180026489  jle     short loc_180026493
0x18002648b  movzx   eax, ax
0x18002648e  or      eax, 80070000h
0x180026493  mov     rcx, [rsp+48h]; this
0x180026498  test    eax, eax
0x18002649a  jns     short loc_1800264B1
0x18002649c  mov     r9d, eax; char *
0x18002649f  lea     r8, aShellcommonInt_2; "shellcommon\\internal\\shell\\inc\\Undo"...
0x1800264a6  mov     edx, 0F6h; void *
0x1800264ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800264b1  mov     rcx, [rsp+48h+buffer]
0x1800264b6  movzx   eax, word ptr [rcx+0Eh]
0x1800264ba  mov     [rdi], ax
0x1800264bd  movzx   eax, word ptr [rcx+0Ch]
0x1800264c1  mov     [rdi+2], ax
0x1800264c5  movzx   eax, word ptr [rcx+0Ah]
0x1800264c9  mov     [rdi+4], ax
0x1800264cd  movzx   eax, word ptr [rcx+8]
0x1800264d1  mov     [rdi+6], ax
0x1800264d5  lea     rcx, [rsp+48h+buffer]
0x1800264da  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800264df  mov     rax, rdi
0x1800264e2  mov     rbx, [rsp+48h+arg_0]
0x1800264e7  add     rsp, 40h
0x1800264eb  pop     rdi
0x1800264ec  retn
0x1800264ed  test    eax, eax
0x1800264ef  jns     short loc_18002650B
0x1800264f1  mov     rcx, [rsp+48h]; this
0x1800264f6  mov     r9d, eax; char *
0x1800264f9  lea     r8, aShellcommonInt_2; "shellcommon\\internal\\shell\\inc\\Undo"...
0x180026500  mov     edx, 0FFh; void *
0x180026505  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002650b  mov     rcx, [rsp+48h]; this
0x180026510  mov     r9d, 80070057h; char *
0x180026516  lea     r8, aShellcommonInt_2; "shellcommon\\internal\\shell\\inc\\Undo"...
0x18002651d  mov     edx, 100h; void *
0x180026522  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
