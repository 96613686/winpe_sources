# ConvertMimeType(ushort const *,tagPROPVARIANT &)

- ea: `0x18002acb0`
- end: `0x18002ad56`
- name: `?ConvertMimeType@@YAJPEBGAEAUtagPROPVARIANT@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002acb0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ace1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ad08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ad33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ace1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ad08`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ad33`

## pseudocode

```c
__int64 __fastcall ConvertMimeType(LPCWCH lpString1, struct tagPROPVARIANT *a2)
{
  a2->vt = 19;
  if ( CompareStringOrdinal(lpString1, -1, L"image/jpeg", -1, 1) == 2 )
  {
    a2->lVal = 2;
  }
  else if ( CompareStringOrdinal(lpString1, -1, L"image/gif", -1, 1) == 2 )
  {
    a2->lVal = 3;
  }
  else
  {
    a2->lVal = CompareStringOrdinal(lpString1, -1, L"image/bmp", -1, 1) == 2;
  }
  return 0;
}

```

## disassembly

```asm
0x18002acb0  mov     [rsp+arg_0], rbx
0x18002acb5  mov     [rsp+arg_8], rsi
0x18002acba  push    rdi
0x18002acbb  sub     rsp, 30h
0x18002acbf  or      esi, 0FFFFFFFFh
0x18002acc2  mov     word ptr [rdx], 13h
0x18002acc7  mov     rbx, rdx
0x18002acca  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002acd2  mov     r9d, esi; cchCount2
0x18002acd5  lea     r8, aImageJpeg; "image/jpeg"
0x18002acdc  mov     edx, esi; cchCount1
0x18002acde  mov     rdi, rcx
0x18002ace1  call    cs:__imp_CompareStringOrdinal
0x18002ace7  cmp     eax, 2
0x18002acea  jnz     short loc_18002ACF1
0x18002acec  mov     [rbx+8], eax
0x18002acef  jmp     short loc_18002AD44
0x18002acf1  mov     r9d, esi; cchCount2
0x18002acf4  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002acfc  lea     r8, aImageGif; "image/gif"
0x18002ad03  mov     edx, esi; cchCount1
0x18002ad05  mov     rcx, rdi; lpString1
0x18002ad08  call    cs:__imp_CompareStringOrdinal
0x18002ad0e  cmp     eax, 2
0x18002ad11  jnz     short loc_18002AD1C
0x18002ad13  mov     dword ptr [rbx+8], 3
0x18002ad1a  jmp     short loc_18002AD44
0x18002ad1c  mov     r9d, esi; cchCount2
0x18002ad1f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002ad27  lea     r8, aImageBmp; "image/bmp"
0x18002ad2e  mov     edx, esi; cchCount1
0x18002ad30  mov     rcx, rdi; lpString1
0x18002ad33  call    cs:__imp_CompareStringOrdinal
0x18002ad39  xor     ecx, ecx
0x18002ad3b  cmp     eax, 2
0x18002ad3e  setz    cl
0x18002ad41  mov     [rbx+8], ecx
0x18002ad44  mov     rbx, [rsp+38h+arg_0]
0x18002ad49  xor     eax, eax
0x18002ad4b  mov     rsi, [rsp+38h+arg_8]
0x18002ad50  add     rsp, 30h
0x18002ad54  pop     rdi
0x18002ad55  retn
```
