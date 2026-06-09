# PortDisconnect

- ea: `0x180013770`
- end: `0x1800138a8`
- name: `PortDisconnect`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d92c`
- `0x180012340`
- `0x180012b00`
- `0x180013770`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013889`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001387f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001387f`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x180013824`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x180013824`

## string_xrefs

- `0x180013813`: `comm/datamodem`

## pseudocode

```c
__int64 __fastcall PortDisconnect(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // ecx
  unsigned int v7; // edi
  unsigned int v8; // eax
  void *v9; // rdx

  if ( !a1 )
  {
    RasTapiTrace("PortDisconnect: hioport==NULL");
    return 2147942487LL;
  }
  GetMutex(a1, a2, a3, a4);
  RasTapiTrace("PortDisconnect: %s");
  v6 = *(_DWORD *)(a1 + 56);
  if ( (unsigned int)(v6 - 3) <= 1 )
    goto LABEL_9;
  if ( v6 != 2 )
  {
    v7 = 0;
    if ( v6 == 5 )
      v7 = 600;
    goto LABEL_11;
  }
  if ( *(_DWORD *)(a1 + 60) )
  {
LABEL_9:
    v8 = InitiatePortDisconnection(a1);
    v9 = *(void **)(a1 + 1080);
    v7 = v8;
    if ( v9 )
    {
      lineSetDevConfigA(*(_DWORD *)(*(_QWORD *)(a1 + 216) + 8LL), v9, *(_DWORD *)(a1 + 1088), "comm/datamodem");
      LocalFree(*(HLOCAL *)(a1 + 1080));
      *(_QWORD *)(a1 + 1080) = 0;
    }
  }
  else
  {
    RasTapiTrace("PortDisconnect: Changing State of %s from %d -> %d");
    v7 = 0;
    *(_DWORD *)(a1 + 56) = 1;
  }
LABEL_11:
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 216) + 32LL) )
  {
    **(_DWORD **)(a1 + 1168) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 1168) + 8LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 1168) + 4LL) = 0;
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  RasTapiTrace(" ");
  return v7;
}

```

## disassembly

```asm
0x180013770  mov     [rsp+arg_0], rbx
0x180013775  push    rdi
0x180013776  sub     rsp, 20h
0x18001377a  mov     rbx, rcx
0x18001377d  test    rcx, rcx
0x180013780  jnz     short loc_180013798
0x180013782  lea     rcx, aPortdisconnect_2; "PortDisconnect: hioport==NULL"
0x180013789  call    RasTapiTrace
0x18001378e  mov     eax, 80070057h
0x180013793  jmp     loc_18001389D
0x180013798  call    GetMutex
0x18001379d  lea     rdx, [rbx+18h]
0x1800137a1  lea     rcx, aPortdisconnect_0; "PortDisconnect: %s"
0x1800137a8  call    RasTapiTrace
0x1800137ad  mov     ecx, [rbx+38h]
0x1800137b0  lea     eax, [rcx-3]
0x1800137b3  cmp     eax, 1
0x1800137b6  jbe     short loc_1800137F6
0x1800137b8  mov     r8d, 2
0x1800137be  cmp     ecx, r8d
0x1800137c1  jnz     short loc_1800137E8
0x1800137c3  cmp     dword ptr [rbx+3Ch], 0
0x1800137c7  jnz     short loc_1800137F6
0x1800137c9  lea     r9d, [r8-1]
0x1800137cd  lea     rdx, [rbx+18h]
0x1800137d1  lea     rcx, aPortdisconnect_1; "PortDisconnect: Changing State of %s fr"...
0x1800137d8  call    RasTapiTrace
0x1800137dd  xor     edi, edi
0x1800137df  mov     dword ptr [rbx+38h], 1
0x1800137e6  jmp     short loc_180013842
0x1800137e8  xor     edi, edi
0x1800137ea  cmp     ecx, 5
0x1800137ed  jnz     short loc_180013842
0x1800137ef  mov     edi, 258h
0x1800137f4  jmp     short loc_180013842
0x1800137f6  mov     rcx, rbx
0x1800137f9  call    InitiatePortDisconnection
0x1800137fe  mov     rdx, [rbx+438h]; lpDeviceConfig
0x180013805  mov     edi, eax
0x180013807  test    rdx, rdx
0x18001380a  jz      short loc_180013842
0x18001380c  mov     rcx, [rbx+0D8h]
0x180013813  lea     r9, SubStr; "comm/datamodem"
0x18001381a  mov     r8d, [rbx+440h]; dwSize
0x180013821  mov     ecx, [rcx+8]; dwDeviceID
0x180013824  call    cs:__imp_lineSetDevConfigA
0x18001382a  mov     rcx, [rbx+438h]; hMem
0x180013831  call    cs:__imp_LocalFree
0x180013837  mov     qword ptr [rbx+438h], 0
0x180013842  mov     rax, [rbx+0D8h]
0x180013849  cmp     dword ptr [rax+20h], 0
0x18001384d  jz      short loc_180013878
0x18001384f  mov     rax, [rbx+490h]
0x180013856  mov     dword ptr [rax], 0
0x18001385c  mov     rax, [rbx+490h]
0x180013863  mov     dword ptr [rax+8], 0
0x18001386a  mov     rax, [rbx+490h]
0x180013871  mov     dword ptr [rax+4], 0
0x180013878  mov     rcx, cs:RasTapiMutex; hMutex
0x18001387f  call    cs:__imp_ReleaseMutex
0x180013885  test    eax, eax
0x180013887  jnz     short loc_18001388F
0x180013889  call    cs:__imp_GetLastError
0x18001388f  lea     rcx, asc_18002C0B8; " "
0x180013896  call    RasTapiTrace
0x18001389b  mov     eax, edi
0x18001389d  mov     rbx, [rsp+28h+arg_0]
0x1800138a2  add     rsp, 20h
0x1800138a6  pop     rdi
0x1800138a7  retn
```
