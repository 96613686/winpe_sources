# SerializeInstanceToBinary

- ea: `0x18002a4bc`
- end: `0x18002a5c5`
- name: `SerializeInstanceToBinary`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027680`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18002a160`
- `0x18002a4bc`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a55c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a55c`
- `mi!mi_clientFT_V1` at `0x18002a517`

## string_xrefs

- `0x18002a550`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall SerializeInstanceToBinary(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, __int64 a5)
{
  __int64 result; // rax
  const MI_SerializerFT *serializerFT; // rax
  unsigned int v9; // ebx
  HMODULE ModuleHandleA; // rax

  *(_WORD *)(a1 + 80) = 0;
  result = SerializeClassDeclOfInstanceToBinary(a1, a2, a3);
  if ( !(_DWORD)result )
  {
    if ( *(_QWORD *)(a1 + 32) == 0xFFEEDDCCFFEEDDCCuLL )
      serializerFT = *(const MI_SerializerFT **)(a1 + 40);
    else
      serializerFT = mi_clientFT_V1->serializerFT;
    v9 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD *, _QWORD, _DWORD, __int64))serializerFT->SerializeInstance)(
           a1 + 32,
           *(_BYTE *)(a1 + 80) != 0 ? 2 : 4,
           a3,
           *(_QWORD *)(a1 + 48),
           *(_DWORD *)(a1 + 56),
           a5);
    if ( v9 )
    {
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(ModuleHandleA, 2014, v9);
      MI_ReportErrorDetails_ForCustomError(21, (int)L"BinaryLogger", 0, 0);
      return v9;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a4bc  mov     [rsp+arg_0], rbx
0x18002a4c1  push    rdi
0x18002a4c2  sub     rsp, 50h
0x18002a4c6  mov     rdi, r8
0x18002a4c9  mov     word ptr [rcx+50h], 0
0x18002a4cf  mov     rbx, rcx
0x18002a4d2  call    SerializeClassDeclOfInstanceToBinary
0x18002a4d7  test    eax, eax
0x18002a4d9  jnz     loc_18002A5BA
0x18002a4df  mov     al, [rbx+50h]
0x18002a4e2  mov     r10d, [rbx+38h]
0x18002a4e6  neg     al
0x18002a4e8  mov     r9, [rbx+30h]
0x18002a4ec  mov     rax, 0FFEEDDCCFFEEDDCCh
0x18002a4f6  sbb     edx, edx
0x18002a4f8  and     edx, 0FFFFFFFEh
0x18002a4fb  add     edx, 4
0x18002a4fe  cmp     [rbx+20h], rax
0x18002a502  jnz     short loc_18002A517
0x18002a504  mov     r8, [rsp+58h+arg_20]
0x18002a50c  mov     rax, [rbx+28h]
0x18002a510  mov     [rsp+58h+var_30], r8
0x18002a515  jmp     short loc_18002A532
0x18002a517  mov     rax, cs:__imp_mi_clientFT_V1
0x18002a51e  mov     rcx, [rax]
0x18002a521  mov     rax, [rcx+20h]
0x18002a525  mov     rcx, [rsp+58h+arg_20]
0x18002a52d  mov     [rsp+58h+var_30], rcx
0x18002a532  mov     rax, [rax+10h]
0x18002a536  lea     rcx, [rbx+20h]
0x18002a53a  mov     r8, rdi
0x18002a53d  mov     dword ptr [rsp+58h+var_38], r10d
0x18002a542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a547  mov     ebx, eax
0x18002a549  test    eax, eax
0x18002a54b  jz      short loc_18002A5B8
0x18002a54d  xorps   xmm0, xmm0
0x18002a550  lea     rcx, ModuleName; "mpunits.dll"
0x18002a557  movups  [rsp+58h+var_18], xmm0
0x18002a55c  call    cs:__imp_GetModuleHandleA
0x18002a562  mov     r8d, ebx
0x18002a565  mov     edx, 7DEh
0x18002a56a  mov     rcx, rax
0x18002a56d  call    _Intlstr_FormatString_FormatMessage
0x18002a572  mov     qword ptr [rsp+58h+var_18], rax
0x18002a577  lea     r9, [rsp+58h+var_18]
0x18002a57c  mov     byte ptr [rsp+58h+var_18+8], 1
0x18002a581  lea     rdx, aBinarylogger; "BinaryLogger"
0x18002a588  movaps  xmm0, [rsp+58h+var_18]
0x18002a58d  mov     r8d, 8
0x18002a593  mov     [rsp+58h+var_30], 0; __int64
0x18002a59c  movdqa  [rsp+58h+var_18], xmm0
0x18002a5a2  mov     [rsp+58h+var_38], 0; __int64
0x18002a5ab  lea     ecx, [r8+0Dh]; int
0x18002a5af  call    MI_ReportErrorDetails_ForCustomError
0x18002a5b4  mov     eax, ebx
0x18002a5b6  jmp     short loc_18002A5BA
0x18002a5b8  xor     eax, eax
0x18002a5ba  mov     rbx, [rsp+58h+arg_0]
0x18002a5bf  add     rsp, 50h
0x18002a5c3  pop     rdi
0x18002a5c4  retn
```
