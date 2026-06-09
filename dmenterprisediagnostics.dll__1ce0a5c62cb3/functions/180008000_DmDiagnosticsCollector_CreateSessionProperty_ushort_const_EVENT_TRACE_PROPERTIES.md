# DmDiagnosticsCollector::CreateSessionProperty(ushort const *,_EVENT_TRACE_PROPERTIES * &)

- ea: `0x180008000`
- end: `0x18000809c`
- name: `?CreateSessionProperty@DmDiagnosticsCollector@@SAJPEBGAEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007ce4`

## callees

- `0x180005a14`
- `0x1800069ec`
- `0x180008000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008015`

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
0x180008000  mov     [rsp+arg_0], rbx
0x180008005  push    rdi; int
0x180008006  sub     rsp, 20h
0x18000800a  mov     rbx, rcx
0x18000800d  mov     rdi, rdx
0x180008010  mov     ecx, 107Ch; cb
0x180008015  call    cs:__imp_CoTaskMemAlloc
0x18000801b  mov     r11, rax
0x18000801e  test    rax, rax
0x180008021  jnz     short loc_180008043
0x180008023  mov     ebx, 8007000Eh
0x180008028  lea     edx, [rax+33h]; void *
0x18000802b  mov     rcx, [rsp+28h]; this
0x180008030  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180008037  mov     r9d, ebx; char *
0x18000803a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000803f  mov     eax, ebx
0x180008041  jmp     short loc_180008091
0x180008043  mov     ecx, 107Ch
0x180008048  mov     byte ptr [rax], 0
0x18000804b  inc     rax
0x18000804e  sub     rcx, 1
0x180008052  jnz     short loc_180008048
0x180008054  lea     rcx, [r11+280h]; unsigned __int16 *
0x18000805b  mov     dword ptr [r11], 107Ch
0x180008062  mov     r8, rbx; unsigned __int16 *
0x180008065  mov     dword ptr [r11+74h], 78h ; 'x'
0x18000806d  mov     edx, 104h; unsigned __int64
0x180008072  mov     dword ptr [r11+70h], 280h
0x18000807a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000807f  mov     ebx, eax
0x180008081  test    eax, eax
0x180008083  jns     short loc_18000808C
0x180008085  mov     edx, 3Dh ; '='
0x18000808a  jmp     short loc_18000802B
0x18000808c  mov     [rdi], r11
0x18000808f  xor     eax, eax
0x180008091  mov     rbx, [rsp+28h+arg_0]
0x180008096  add     rsp, 20h
0x18000809a  pop     rdi
0x18000809b  retn
```
