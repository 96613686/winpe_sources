# CsvtaskHandler::_FmifsCallback(_FMIFS_PACKET_TYPE,ulong,void *)

- ea: `0x1800026b0`
- end: `0x180002722`
- name: `?_FmifsCallback@CsvtaskHandler@@CAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z`
- size: `114`
- prototype: `char __fastcall(int, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800026b0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800026cf`
- `KERNEL32!TlsGetValue` at `0x1800026cf`

## pseudocode

```c
char __fastcall CsvtaskHandler::_FmifsCallback(int a1, __int64 a2, _DWORD *a3)
{
  char v5; // di
  volatile signed __int32 *Value; // rax
  bool v7; // dl
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx

  v5 = 1;
  Value = (volatile signed __int32 *)TlsGetValue(g_iTLSChkDskThreadData);
  if ( Value )
  {
    v7 = _InterlockedCompareExchange(Value + 9, 1, 1) != 1;
    v8 = a1 - 6;
    if ( !v8 )
      return 0;
    v9 = v8 - 1;
    if ( !v9 )
      return 0;
    v10 = v9 - 3;
    if ( !v10 )
      return 0;
    v11 = v10 - 1;
    if ( !v11 )
    {
      *((_DWORD *)Value + 14) = a3[1];
      return *(_BYTE *)a3;
    }
    if ( v11 == 21 )
      return 0;
    return v7;
  }
  return v5;
}

```

## disassembly

```asm
0x1800026b0  mov     [rsp+arg_0], rbx
0x1800026b5  mov     [rsp+arg_8], rsi
0x1800026ba  push    rdi
0x1800026bb  sub     rsp, 20h
0x1800026bf  mov     ebx, ecx
0x1800026c1  mov     rsi, r8
0x1800026c4  mov     ecx, cs:?g_iTLSChkDskThreadData@@3KA; dwTlsIndex
0x1800026ca  mov     edi, 1
0x1800026cf  call    cs:__imp_TlsGetValue
0x1800026d5  mov     r9, rax
0x1800026d8  test    rax, rax
0x1800026db  jz      short loc_180002704
0x1800026dd  mov     eax, edi
0x1800026df  lock cmpxchg [r9+24h], edi
0x1800026e5  setnz   dl
0x1800026e8  sub     ebx, 6
0x1800026eb  jz      short loc_1800026FF
0x1800026ed  sub     ebx, edi
0x1800026ef  jz      short loc_1800026FF
0x1800026f1  sub     ebx, 3
0x1800026f4  jz      short loc_1800026FF
0x1800026f6  sub     ebx, edi
0x1800026f8  jz      short loc_180002717
0x1800026fa  cmp     ebx, 15h
0x1800026fd  jnz     short loc_180002701
0x1800026ff  xor     dl, dl
0x180002701  mov     dil, dl
0x180002704  mov     rbx, [rsp+28h+arg_0]
0x180002709  mov     al, dil
0x18000270c  mov     rsi, [rsp+28h+arg_8]
0x180002711  add     rsp, 20h
0x180002715  pop     rdi
0x180002716  retn
0x180002717  mov     eax, [rsi+4]
0x18000271a  mov     [r9+38h], eax
0x18000271e  mov     dl, [rsi]
0x180002720  jmp     short loc_180002701
```
