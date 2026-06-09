# DmDiagnosticsCollector::CreateSessionProperty(ushort const *,_EVENT_TRACE_PROPERTIES * &)

- ea: `0x1800083a0`
- end: `0x180008443`
- name: `?CreateSessionProperty@DmDiagnosticsCollector@@SAJPEBGAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008064`

## callees

- `0x180005c14`
- `0x180006c6c`
- `0x1800083a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800083b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800083b5`

## pseudocode

```c
__int64 __fastcall DmDiagnosticsCollector::CreateSessionProperty(
        const unsigned __int16 *a1,
        struct _EVENT_TRACE_PROPERTIES **a2)
{
  _BYTE *v4; // rax
  _BYTE *v5; // r11
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // rcx
  struct _EVENT_TRACE_PROPERTIES *v10; // r11
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = CoTaskMemAlloc(0x107Cu);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    v7 = 51;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisediagnosticsetw\\lib\\dmdiagnosticscollector.cpp",
      (const char *)(unsigned int)v6,
      v11);
    return (unsigned int)v6;
  }
  v9 = 4220;
  do
  {
    *v4++ = 0;
    --v9;
  }
  while ( v9 );
  *(_DWORD *)v5 = 4220;
  *((_DWORD *)v5 + 29) = 120;
  *((_DWORD *)v5 + 28) = 640;
  v6 = StringCchCopyW((unsigned __int16 *)v5 + 320, 0x104u, a1);
  if ( v6 < 0 )
  {
    v7 = 61;
    goto LABEL_3;
  }
  *a2 = v10;
  return 0;
}

```

## disassembly

```asm
0x1800083a0  mov     [rsp+arg_0], rbx
0x1800083a5  push    rdi; int
0x1800083a6  sub     rsp, 20h
0x1800083aa  mov     rbx, rcx
0x1800083ad  mov     rdi, rdx
0x1800083b0  mov     ecx, 107Ch; cb
0x1800083b5  call    cs:__imp_CoTaskMemAlloc
0x1800083bc  nop     dword ptr [rax+rax+00h]
0x1800083c1  mov     r11, rax
0x1800083c4  test    rax, rax
0x1800083c7  jnz     short loc_1800083E9
0x1800083c9  mov     ebx, 8007000Eh
0x1800083ce  lea     edx, [rax+33h]; void *
0x1800083d1  mov     rcx, [rsp+28h]; this
0x1800083d6  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800083dd  mov     r9d, ebx; char *
0x1800083e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800083e5  mov     eax, ebx
0x1800083e7  jmp     short loc_180008437
0x1800083e9  mov     ecx, 107Ch
0x1800083ee  mov     byte ptr [rax], 0
0x1800083f1  inc     rax
0x1800083f4  sub     rcx, 1
0x1800083f8  jnz     short loc_1800083EE
0x1800083fa  lea     rcx, [r11+280h]; unsigned __int16 *
0x180008401  mov     dword ptr [r11], 107Ch
0x180008408  mov     r8, rbx; unsigned __int16 *
0x18000840b  mov     dword ptr [r11+74h], 78h ; 'x'
0x180008413  mov     edx, 104h; unsigned __int64
0x180008418  mov     dword ptr [r11+70h], 280h
0x180008420  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008425  mov     ebx, eax
0x180008427  test    eax, eax
0x180008429  jns     short loc_180008432
0x18000842b  mov     edx, 3Dh ; '='
0x180008430  jmp     short loc_1800083D1
0x180008432  mov     [rdi], r11
0x180008435  xor     eax, eax
0x180008437  mov     rbx, [rsp+28h+arg_0]
0x18000843c  add     rsp, 20h
0x180008440  pop     rdi
0x180008441  retn
```
