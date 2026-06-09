# ServiceHandler

- ea: `0x18000b7e0`
- end: `0x18000b8d4`
- name: `ServiceHandler`
- size: `244`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000b7e0`
- `0x18000bc1c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b8c7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b8c7`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  __int64 result; // rax
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // ecx
  void (__fastcall *v11)(_QWORD, __int64, LPVOID, LPVOID); // rcx

  result = 120;
  v5 = dwControl - 1;
  if ( !v5 )
  {
    SvcFrameworkUpdateServiceStatus(3u, 0, 0x32u);
    if ( hObject )
      SetEvent(hObject);
    return 0;
  }
  v6 = v5 - 3;
  if ( !v6 )
    return 0;
  v7 = v6 - 1;
  if ( !v7 )
  {
    v11 = (void (__fastcall *)(_QWORD, __int64, LPVOID, LPVOID))qword_180018648;
    goto LABEL_14;
  }
  v8 = v7 - 8;
  if ( !(_DWORD)v8 )
  {
    if ( (_DWORD)dwEventType == 32787 )
    {
      if ( qword_180018640 && lpEventData )
        return qword_180018640(lpEventData);
    }
    else if ( (_DWORD)dwEventType == 10 && qword_180018630 )
    {
      return qword_180018630(v8, dwEventType, lpEventData, lpContext);
    }
    return 0;
  }
  v9 = v8 - 2;
  if ( !v9 )
  {
    v11 = (void (__fastcall *)(_QWORD, __int64, LPVOID, LPVOID))qword_1800185E8;
LABEL_14:
    if ( !v11 )
      return result;
    v11(v11, dwEventType, lpEventData, lpContext);
    return 0;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( !qword_180018628 )
      return result;
    ((void (__fastcall *)(LPVOID))qword_180018628)(lpEventData);
    return 0;
  }
  if ( v10 == 16 )
  {
    result = 0;
    if ( ServiceStatus.dwCurrentState == 3 )
      return 1115;
  }
  return result;
}

```

## disassembly

```asm
0x18000b7e0  sub     rsp, 28h
0x18000b7e4  mov     eax, 78h ; 'x'
0x18000b7e9  sub     ecx, 1
0x18000b7ec  jz      loc_18000B8AD
0x18000b7f2  sub     ecx, 3
0x18000b7f5  jz      loc_18000B8CD
0x18000b7fb  sub     ecx, 1
0x18000b7fe  jz      loc_18000B8A4
0x18000b804  sub     ecx, 8
0x18000b807  jz      short loc_18000B865
0x18000b809  sub     ecx, 2
0x18000b80c  jz      short loc_18000B84F
0x18000b80e  sub     ecx, 1
0x18000b811  jz      short loc_18000B832
0x18000b813  cmp     ecx, 10h
0x18000b816  jnz     loc_18000B8CF
0x18000b81c  xor     eax, eax
0x18000b81e  mov     ecx, 45Bh
0x18000b823  cmp     cs:ServiceStatus.dwCurrentState, 3
0x18000b82a  cmovz   eax, ecx
0x18000b82d  jmp     loc_18000B8CF
0x18000b832  mov     rdx, cs:qword_180018628
0x18000b839  test    rdx, rdx
0x18000b83c  jz      loc_18000B8CF
0x18000b842  mov     rcx, r8
0x18000b845  mov     rax, rdx
0x18000b848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b84d  jmp     short loc_18000B8CD
0x18000b84f  mov     rcx, cs:qword_1800185E8
0x18000b856  test    rcx, rcx
0x18000b859  jz      short loc_18000B8CF
0x18000b85b  mov     rax, rcx
0x18000b85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b863  jmp     short loc_18000B8CD
0x18000b865  cmp     edx, 8013h
0x18000b86b  jnz     short loc_18000B88A
0x18000b86d  mov     rax, cs:qword_180018640
0x18000b874  test    rax, rax
0x18000b877  jz      short loc_18000B8CD
0x18000b879  test    r8, r8
0x18000b87c  jz      short loc_18000B8CD
0x18000b87e  mov     rcx, r8
0x18000b881  add     rsp, 28h
0x18000b885  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000b88a  cmp     edx, 0Ah
0x18000b88d  jnz     short loc_18000B8CD
0x18000b88f  mov     rax, cs:qword_180018630
0x18000b896  test    rax, rax
0x18000b899  jz      short loc_18000B8CD
0x18000b89b  add     rsp, 28h
0x18000b89f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a4  mov     rcx, cs:qword_180018648
0x18000b8ab  jmp     short loc_18000B856
0x18000b8ad  xor     edx, edx; unsigned int
0x18000b8af  lea     ecx, [rdx+3]; unsigned int
0x18000b8b2  lea     r8d, [rdx+32h]; unsigned int
0x18000b8b6  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000b8bb  mov     rcx, cs:hObject; hEvent
0x18000b8c2  test    rcx, rcx
0x18000b8c5  jz      short loc_18000B8CD
0x18000b8c7  call    cs:__imp_SetEvent
0x18000b8cd  xor     eax, eax
0x18000b8cf  add     rsp, 28h
0x18000b8d3  retn
```
