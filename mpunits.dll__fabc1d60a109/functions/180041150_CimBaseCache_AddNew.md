# CimBaseCache_AddNew

- ea: `0x180041150`
- end: `0x18004120e`
- name: `CimBaseCache_AddNew`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180041150`
- `0x180043e08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800411b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800411b3`

## string_xrefs

- `0x1800411a4`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall CimBaseCache_AddNew(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  unsigned __int16 *v4; // rdx
  __int64 result; // rax
  __int64 v6; // rbx
  HMODULE ModuleHandleA; // rax

  v2 = -1;
  a2[3] = a1;
  v4 = (unsigned __int16 *)a2[6];
  do
    ++v2;
  while ( v4[v2] );
  a2[1] = *v4 + (((v2 << 8) + v4[v2 - 1]) << 8);
  result = HashMap_Insert(a1, a2);
  if ( (_DWORD)result )
  {
    v6 = a2[6];
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    Intlstr_FormatString_FormatMessage(ModuleHandleA, 2132, v6);
    return MI_ReportErrorDetails_ForCustomError(11, (int)L"MI", 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180041150  mov     [rsp+arg_0], rbx
0x180041155  push    rdi
0x180041156  sub     rsp, 40h
0x18004115a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004115e  mov     [rdx+18h], rcx
0x180041162  mov     rbx, rdx
0x180041165  xor     edi, edi
0x180041167  mov     rdx, [rdx+30h]
0x18004116b  mov     r8, rcx
0x18004116e  inc     rax
0x180041171  cmp     [rdx+rax*2], di
0x180041175  jnz     short loc_18004116E
0x180041177  movzx   ecx, word ptr [rdx+rax*2-2]
0x18004117c  shl     rax, 8
0x180041180  add     rcx, rax
0x180041183  movzx   eax, word ptr [rdx]
0x180041186  shl     rcx, 8
0x18004118a  mov     rdx, rbx
0x18004118d  add     rcx, rax
0x180041190  mov     [rbx+8], rcx
0x180041194  mov     rcx, r8
0x180041197  call    HashMap_Insert
0x18004119c  test    eax, eax
0x18004119e  jz      short loc_180041203
0x1800411a0  mov     rbx, [rbx+30h]
0x1800411a4  lea     rcx, ModuleName; "mpunits.dll"
0x1800411ab  xorps   xmm0, xmm0
0x1800411ae  movups  [rsp+48h+var_18], xmm0
0x1800411b3  call    cs:__imp_GetModuleHandleA
0x1800411b9  mov     r8, rbx
0x1800411bc  mov     edx, 854h
0x1800411c1  mov     rcx, rax
0x1800411c4  call    _Intlstr_FormatString_FormatMessage
0x1800411c9  mov     qword ptr [rsp+48h+var_18], rax
0x1800411ce  lea     r9, [rsp+48h+var_18]
0x1800411d3  mov     byte ptr [rsp+48h+var_18+8], 1
0x1800411d8  lea     rdx, aMi; "MI"
0x1800411df  movaps  xmm0, [rsp+48h+var_18]
0x1800411e4  mov     r8d, 14h
0x1800411ea  mov     [rsp+48h+var_20], rdi; __int64
0x1800411ef  movdqa  [rsp+48h+var_18], xmm0
0x1800411f5  mov     [rsp+48h+var_28], rdi; __int64
0x1800411fa  lea     ecx, [r8-9]; int
0x1800411fe  call    MI_ReportErrorDetails_ForCustomError
0x180041203  mov     rbx, [rsp+48h+arg_0]
0x180041208  add     rsp, 40h
0x18004120c  pop     rdi
0x18004120d  retn
```
