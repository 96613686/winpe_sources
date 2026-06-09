# CIncomingConnectionsTask::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x18001f960`
- end: `0x18001fa0a`
- name: `?CanHostTask@CIncomingConnectionsTask@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(CIncomingConnectionsTask *__hidden this, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001f8ec`
- `0x18001f960`
- `0x18002f382`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001f9f7`
- `rtutils!TracePrintfExA` at `0x18001f9f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f985`

## string_xrefs

- `0x18001f9eb`: `CIncomingConnectionsTask::CanHostTask: returns hr = %#x`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionsTask::CanHostTask(
        CIncomingConnectionsTask *this,
        struct _GUID *const a2,
        struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const a3)
{
  unsigned int v4; // ebx
  _DWORD *v5; // rax
  _DWORD *v6; // rbx

  if ( (unsigned int)CIncomingConnectionsTask::CanAllowICC(this) )
  {
    v4 = 0;
    if ( a3 )
    {
      v5 = CoTaskMemAlloc(0x40u);
      v6 = v5;
      if ( v5 )
      {
        memset_0(v5, 0, 0x40u);
        *v6 = 64;
        v6[1] = 3;
        *((_QWORD *)v6 + 4) = hInst;
        *((_QWORD *)v6 + 5) = 10011;
        *((_QWORD *)v6 + 6) = 3040;
        *((_QWORD *)v6 + 7) = 3041;
        *a3 = (struct _XWIZARD_HOST_DISPLAY_TASK_INFO *)v6;
        v4 = 0;
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  else
  {
    v4 = 1;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CIncomingConnectionsTask::CanHostTask: returns hr = %#x", v4);
  return v4;
}

```

## disassembly

```asm
0x18001f960  mov     [rsp+arg_0], rbx
0x18001f965  push    rdi
0x18001f966  sub     rsp, 20h
0x18001f96a  mov     rdi, r8
0x18001f96d  call    ?CanAllowICC@CIncomingConnectionsTask@@IEAAHXZ; CIncomingConnectionsTask::CanAllowICC(void)
0x18001f972  test    eax, eax
0x18001f974  jnz     short loc_18001F97B
0x18001f976  lea     ebx, [rax+1]
0x18001f979  jmp     short loc_18001F9DD
0x18001f97b  xor     ebx, ebx
0x18001f97d  test    rdi, rdi
0x18001f980  jz      short loc_18001F9DD
0x18001f982  lea     ecx, [rbx+40h]; cb
0x18001f985  call    cs:__imp_CoTaskMemAlloc
0x18001f98b  mov     rbx, rax
0x18001f98e  test    rax, rax
0x18001f991  jz      short loc_18001F9D8
0x18001f993  xor     edx, edx; Val
0x18001f995  mov     rcx, rax; void *
0x18001f998  lea     r8d, [rdx+40h]; Size
0x18001f99c  call    memset_0
0x18001f9a1  mov     dword ptr [rbx], 40h ; '@'
0x18001f9a7  mov     dword ptr [rbx+4], 3
0x18001f9ae  mov     rcx, cs:hInst
0x18001f9b5  mov     [rbx+20h], rcx
0x18001f9b9  mov     qword ptr [rbx+28h], 271Bh
0x18001f9c1  mov     qword ptr [rbx+30h], 0BE0h
0x18001f9c9  mov     qword ptr [rbx+38h], 0BE1h
0x18001f9d1  mov     [rdi], rbx
0x18001f9d4  xor     ebx, ebx
0x18001f9d6  jmp     short loc_18001F9DD
0x18001f9d8  mov     ebx, 8007000Eh
0x18001f9dd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f9e3  cmp     ecx, 0FFFFFFFFh
0x18001f9e6  jz      short loc_18001F9FD
0x18001f9e8  mov     r9d, ebx
0x18001f9eb  lea     r8, aCincomingconne_2; "CIncomingConnectionsTask::CanHostTask: "...
0x18001f9f2  mov     edx, 0Ch; dwFlags
0x18001f9f7  call    cs:__imp_TracePrintfExA
0x18001f9fd  mov     eax, ebx
0x18001f9ff  mov     rbx, [rsp+28h+arg_0]
0x18001fa04  add     rsp, 20h
0x18001fa08  pop     rdi
0x18001fa09  retn
```
