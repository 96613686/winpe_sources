# Subscription_SetType

- ea: `0x180040ff8`
- end: `0x1800410b0`
- name: `Subscription_SetType`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180040e2c`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180040ff8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180041037`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180041037`

## string_xrefs

- `0x180041025`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Subscription_SetType(__int64 a1)
{
  __int64 v1; // rbx
  unsigned int v2; // edi
  __int64 v3; // rbx
  HMODULE ModuleHandleA; // rax

  v1 = *(_QWORD *)(a1 + 72);
  v2 = 0;
  if ( *(_WORD *)(v1 + 162) )
  {
    if ( *(_WORD *)(v1 + 162) == 2 )
    {
      *(_DWORD *)(a1 + 80) = 1;
    }
    else if ( *(_WORD *)(v1 + 162) == 3 )
    {
      *(_DWORD *)(a1 + 80) = 2;
    }
    else
    {
      v3 = *(_QWORD *)(v1 + 48);
      v2 = -1;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(ModuleHandleA, 2130, v3);
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    }
  }
  else
  {
    *(_DWORD *)(a1 + 80) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180040ff8  mov     [rsp+arg_0], rbx
0x180040ffd  push    rdi
0x180040ffe  sub     rsp, 40h
0x180041002  mov     rbx, [rcx+48h]
0x180041006  xor     edi, edi
0x180041008  movzx   edx, word ptr [rbx+0A2h]
0x18004100f  test    edx, edx
0x180041011  jz      loc_1800410A0
0x180041017  sub     edx, 2
0x18004101a  jz      short loc_180041097
0x18004101c  cmp     edx, 1
0x18004101f  jz      short loc_18004108E
0x180041021  mov     rbx, [rbx+30h]
0x180041025  lea     rcx, ModuleName; "mpunits.dll"
0x18004102c  xorps   xmm0, xmm0
0x18004102f  or      edi, 0FFFFFFFFh
0x180041032  movups  [rsp+48h+var_18], xmm0
0x180041037  call    cs:__imp_GetModuleHandleA
0x18004103d  mov     r8, rbx
0x180041040  mov     edx, 852h
0x180041045  mov     rcx, rax
0x180041048  call    _Intlstr_FormatString_FormatMessage
0x18004104d  mov     qword ptr [rsp+48h+var_18], rax
0x180041052  lea     r9, [rsp+48h+var_18]
0x180041057  mov     byte ptr [rsp+48h+var_18+8], 1
0x18004105c  lea     r8d, [rdi+6]
0x180041060  movaps  xmm0, [rsp+48h+var_18]
0x180041065  lea     rdx, aMi; "MI"
0x18004106c  mov     [rsp+48h+var_20], 0; __int64
0x180041075  lea     ecx, [rdi+5]; int
0x180041078  movdqa  [rsp+48h+var_18], xmm0
0x18004107e  mov     [rsp+48h+var_28], 0; __int64
0x180041087  call    MI_ReportErrorDetails_ForCustomError
0x18004108c  jmp     short loc_1800410A3
0x18004108e  mov     dword ptr [rcx+50h], 2
0x180041095  jmp     short loc_1800410A3
0x180041097  mov     dword ptr [rcx+50h], 1
0x18004109e  jmp     short loc_1800410A3
0x1800410a0  mov     [rcx+50h], edi
0x1800410a3  mov     rbx, [rsp+48h+arg_0]
0x1800410a8  mov     eax, edi
0x1800410aa  add     rsp, 40h
0x1800410ae  pop     rdi
0x1800410af  retn
```
