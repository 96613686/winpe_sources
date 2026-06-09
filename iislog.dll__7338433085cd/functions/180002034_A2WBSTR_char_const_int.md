# A2WBSTR(char const *,int)

- ea: `0x180002034`
- end: `0x1800020bf`
- name: `?A2WBSTR@@YAPEAGPEBDH@Z`
- size: `139`
- prototype: `unsigned __int16 *__fastcall(LPCCH lpMultiByteStr, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b80`
- `0x180008bf0`
- `0x180008c70`
- `0x180008e30`
- `0x180008f30`
- `0x180008fb0`
- `0x180009030`
- `0x1800090b0`
- `0x1800091b0`
- `0x1800092b0`
- `0x180009330`
- `0x1800093b0`
- `0x180009430`

## callees

- `0x180002034`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180002066`
- `KERNEL32!MultiByteToWideChar` at `0x180002095`
- `KERNEL32!MultiByteToWideChar` at `0x180002066`
- `KERNEL32!MultiByteToWideChar` at `0x180002095`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002073`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180002073`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800020a2`

## pseudocode

```c
unsigned __int16 *__fastcall A2WBSTR(LPCCH lpMultiByteStr)
{
  int cchWideChar; // esi
  WCHAR *lpWideCharStr; // rax
  OLECHAR *v4; // rbx

  if ( !lpMultiByteStr )
    return 0;
  cchWideChar = MultiByteToWideChar(0, 0, lpMultiByteStr, -1, 0, 0);
  lpWideCharStr = SysAllocStringLen(0, cchWideChar - 1);
  v4 = lpWideCharStr;
  if ( lpWideCharStr && MultiByteToWideChar(0, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) != cchWideChar )
  {
    SysFreeString(v4);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180002034  mov     rax, rsp
0x180002037  mov     [rax+8], rbx
0x18000203b  mov     [rax+10h], rsi
0x18000203f  push    rdi
0x180002040  sub     rsp, 30h
0x180002044  mov     rdi, rcx
0x180002047  test    rcx, rcx
0x18000204a  jz      short loc_1800020A8
0x18000204c  mov     r8, rcx; lpMultiByteStr
0x18000204f  mov     dword ptr [rax-10h], 0
0x180002056  xor     ecx, ecx; CodePage
0x180002058  mov     qword ptr [rax-18h], 0
0x180002060  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180002064  xor     edx, edx; dwFlags
0x180002066  call    cs:__imp_MultiByteToWideChar
0x18000206c  xor     ecx, ecx; strIn
0x18000206e  mov     esi, eax
0x180002070  lea     edx, [rax-1]; ui
0x180002073  call    cs:__imp_SysAllocStringLen
0x180002079  mov     rbx, rax
0x18000207c  test    rax, rax
0x18000207f  jz      short loc_1800020BA
0x180002081  mov     [rsp+38h+cchWideChar], esi; cchWideChar
0x180002085  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180002089  mov     r8, rdi; lpMultiByteStr
0x18000208c  mov     [rsp+38h+lpWideCharStr], rax; lpWideCharStr
0x180002091  xor     edx, edx; dwFlags
0x180002093  xor     ecx, ecx; CodePage
0x180002095  call    cs:__imp_MultiByteToWideChar
0x18000209b  cmp     eax, esi
0x18000209d  jz      short loc_1800020BA
0x18000209f  mov     rcx, rbx; bstrString
0x1800020a2  call    cs:__imp_SysFreeString
0x1800020a8  xor     eax, eax
0x1800020aa  mov     rbx, [rsp+38h+arg_0]
0x1800020af  mov     rsi, [rsp+38h+arg_8]
0x1800020b4  add     rsp, 30h
0x1800020b8  pop     rdi
0x1800020b9  retn
0x1800020ba  mov     rax, rbx
0x1800020bd  jmp     short loc_1800020AA
```
