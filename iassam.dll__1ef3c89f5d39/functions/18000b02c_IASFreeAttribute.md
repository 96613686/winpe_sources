# IASFreeAttribute

- ea: `0x18000b02c`
- end: `0x18000b085`
- name: `IASFreeAttribute`
- size: `89`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ae5c`
- `0x18000b08c`
- `0x18002bb99`

## callees

- `0x18000b02c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b070`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b079`

## pseudocode

```c
void __fastcall IASFreeAttribute(_DWORD *pv)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  void *v5; // rcx
  void *v6; // rcx

  if ( pv )
  {
    v2 = pv[4] - 4;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( !v4 )
        {
          v5 = (void *)*((_QWORD *)pv + 4);
          goto LABEL_11;
        }
        if ( v4 != 4 )
        {
LABEL_13:
          CoTaskMemFree(pv);
          return;
        }
      }
      else
      {
        v6 = (void *)*((_QWORD *)pv + 4);
        if ( v6 )
          CoTaskMemFree(v6);
      }
    }
    v5 = (void *)*((_QWORD *)pv + 3);
LABEL_11:
    if ( v5 )
      CoTaskMemFree(v5);
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18000b02c  test    rcx, rcx
0x18000b02f  jz      short locret_18000B084
0x18000b031  push    rbx
0x18000b032  sub     rsp, 20h
0x18000b036  mov     rbx, rcx
0x18000b039  mov     ecx, [rcx+10h]
0x18000b03c  sub     ecx, 4
0x18000b03f  jz      short loc_18000B067
0x18000b041  sub     ecx, 1
0x18000b044  jz      short loc_18000B058
0x18000b046  sub     ecx, 1
0x18000b049  jz      short loc_18000B052
0x18000b04b  cmp     ecx, 4
0x18000b04e  jz      short loc_18000B067
0x18000b050  jmp     short loc_18000B076
0x18000b052  mov     rcx, [rbx+20h]
0x18000b056  jmp     short loc_18000B06B
0x18000b058  mov     rcx, [rbx+20h]; pv
0x18000b05c  test    rcx, rcx
0x18000b05f  jz      short loc_18000B067
0x18000b061  call    cs:__imp_CoTaskMemFree
0x18000b067  mov     rcx, [rbx+18h]; pv
0x18000b06b  test    rcx, rcx
0x18000b06e  jz      short loc_18000B076
0x18000b070  call    cs:__imp_CoTaskMemFree
0x18000b076  mov     rcx, rbx; pv
0x18000b079  call    cs:__imp_CoTaskMemFree
0x18000b07f  add     rsp, 20h
0x18000b083  pop     rbx
0x18000b084  retn
```
