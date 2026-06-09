# GetTempBuffer

- ea: `0x14000d900`
- end: `0x14000d989`
- name: `GetTempBuffer`
- size: `137`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000cf2c`
- `0x14000df14`
- `0x14000e050`

## callees

- `0x14000d3e8`
- `0x14000d900`
- `0x14000f4d8`
- `0x14000f51c`
- `0x14000f568`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000d95b`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000d95b`

## pseudocode

```c
__int64 __fastcall GetTempBuffer(__int64 a1, WCHAR *a2, unsigned int a3, int a4)
{
  unsigned int Count2; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // r11d
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // r11d
  __int64 v11; // rax
  __int64 v12; // rbx

  if ( a2 || a3 || a4 )
    return GetInternalTemporaryBuffer(a1, a2, a3, a4);
  if ( g_bInitialized )
  {
    Count2 = DynArrayGetCount2(a1, 3);
    if ( Count2 > v7 )
    {
      if ( (unsigned int)DynArrayGetItemType2(v6, v5, v7) )
      {
        v11 = DynArrayItem2(v9, v8, v10);
        v12 = v11;
        if ( v11 )
        {
          if ( !(unsigned int)_o__memicmp(v11, "BUFFER", 7) )
            return *(_QWORD *)(v12 + 16);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d900  push    rbx
0x14000d902  sub     rsp, 20h
0x14000d906  mov     r11d, ecx
0x14000d909  test    rdx, rdx
0x14000d90c  jnz     short loc_14000D97F
0x14000d90e  test    r8d, r8d
0x14000d911  jnz     short loc_14000D97F
0x14000d913  test    r9d, r9d
0x14000d916  jnz     short loc_14000D97F
0x14000d918  cmp     cs:g_bInitialized, r9d
0x14000d91f  jz      short loc_14000D976
0x14000d921  lea     edx, [r8+3]
0x14000d925  call    DynArrayGetCount2
0x14000d92a  cmp     eax, r11d
0x14000d92d  jbe     short loc_14000D976
0x14000d92f  mov     r8d, r11d
0x14000d932  call    DynArrayGetItemType2
0x14000d937  test    eax, eax
0x14000d939  jz      short loc_14000D976
0x14000d93b  mov     r8d, r11d
0x14000d93e  call    DynArrayItem2
0x14000d943  mov     rbx, rax
0x14000d946  test    rax, rax
0x14000d949  jz      short loc_14000D976
0x14000d94b  mov     r8d, 7
0x14000d951  lea     rdx, cszSignature; "BUFFER"
0x14000d958  mov     rcx, rax
0x14000d95b  call    cs:__imp__o__memicmp
0x14000d962  nop     dword ptr [rax+rax+00h]
0x14000d967  test    eax, eax
0x14000d969  jnz     short loc_14000D976
0x14000d96b  mov     rax, [rbx+10h]
0x14000d96f  add     rsp, 20h
0x14000d973  pop     rbx
0x14000d974  retn
0x14000d976  xor     eax, eax
0x14000d978  add     rsp, 20h
0x14000d97c  pop     rbx
0x14000d97d  retn
0x14000d97f  add     rsp, 20h
0x14000d983  pop     rbx
0x14000d984  jmp     GetInternalTemporaryBuffer
```
