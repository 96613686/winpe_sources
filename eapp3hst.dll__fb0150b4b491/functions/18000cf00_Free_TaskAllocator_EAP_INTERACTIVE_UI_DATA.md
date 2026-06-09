# Free<TaskAllocator>(_EAP_INTERACTIVE_UI_DATA &)

- ea: `0x18000cf00`
- end: `0x18000cf6f`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000caec`
- `0x18000d124`
- `0x18000e5e0`
- `0x18001f7e0`
- `0x180030e61`

## callees

- `0x18000ce64`
- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf40`

## pseudocode

```c
__int64 __fastcall Free<TaskAllocator>(__int64 a1)
{
  int v2; // edx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // rbx

  if ( *(_DWORD *)(a1 + 12) )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( !v2 )
      goto LABEL_7;
    v3 = v2 - 1;
    if ( !v3 )
      goto LABEL_7;
    v4 = v3 - 1;
    if ( !v4 || (v5 = v4 - 1) == 0 )
    {
      v8 = *(_QWORD *)(a1 + 16);
      Free<TaskAllocator>(v8);
      v6 = v8 + 16;
      goto LABEL_8;
    }
    if ( (unsigned int)(v5 - 1) <= 1 )
    {
LABEL_7:
      v6 = *(_QWORD *)(a1 + 16);
LABEL_8:
      Free<TaskAllocator>(v6);
      CoTaskMemFree(*(LPVOID *)(a1 + 16));
    }
  }
  result = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18000cf00  mov     [rsp+arg_0], rbx
0x18000cf05  push    rdi
0x18000cf06  sub     rsp, 20h
0x18000cf0a  cmp     dword ptr [rcx+0Ch], 0
0x18000cf0e  mov     rdi, rcx
0x18000cf11  jz      short loc_18000CF46
0x18000cf13  mov     edx, [rcx+8]
0x18000cf16  test    edx, edx
0x18000cf18  jz      short loc_18000CF33
0x18000cf1a  sub     edx, 1
0x18000cf1d  jz      short loc_18000CF33
0x18000cf1f  sub     edx, 1
0x18000cf22  jz      short loc_18000CF5D
0x18000cf24  sub     edx, 1
0x18000cf27  jz      short loc_18000CF5D
0x18000cf29  sub     edx, 1
0x18000cf2c  jz      short loc_18000CF33
0x18000cf2e  cmp     edx, 1
0x18000cf31  jnz     short loc_18000CF46
0x18000cf33  mov     rcx, [rcx+10h]
0x18000cf37  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18000cf3c  mov     rcx, [rdi+10h]; pv
0x18000cf40  call    cs:__imp_CoTaskMemFree
0x18000cf46  mov     rbx, [rsp+28h+arg_0]
0x18000cf4b  xorps   xmm0, xmm0
0x18000cf4e  xor     eax, eax
0x18000cf50  movups  xmmword ptr [rdi], xmm0
0x18000cf53  mov     [rdi+10h], rax
0x18000cf57  add     rsp, 20h
0x18000cf5b  pop     rdi
0x18000cf5c  retn
0x18000cf5d  mov     rbx, [rcx+10h]
0x18000cf61  mov     rcx, rbx
0x18000cf64  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18000cf69  lea     rcx, [rbx+10h]
0x18000cf6d  jmp     short loc_18000CF37
```
