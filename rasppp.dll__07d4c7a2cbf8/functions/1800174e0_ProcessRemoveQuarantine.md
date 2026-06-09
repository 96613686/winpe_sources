# ProcessRemoveQuarantine

- ea: `0x1800174e0`
- end: `0x18001763b`
- name: `ProcessRemoveQuarantine`
- size: `347`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000f334`
- `0x18000f528`
- `0x1800109a0`
- `0x1800174e0`
- `0x18002a138`

## string_xrefs

- `0x180017563`: `ProcessRemoveQuarantine: removing quarantine-session-timer`
- `0x1800175a6`: `ProcessRemoveQuarantine: adding session timeout %d`

## pseudocode

```c
_QWORD *__fastcall ProcessRemoveQuarantine(__int64 a1)
{
  __int64 BCBPointerFromhConnection; // rax
  __int64 v2; // rbx
  _QWORD *result; // rax
  __int64 i; // rdi
  __int64 v5; // rsi
  int v6; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v7[2044]; // [rsp+54h] [rbp-814h] BYREF

  BCBPointerFromhConnection = GetBCBPointerFromhConnection(*(_QWORD *)(a1 + 24));
  v6 = 0;
  v2 = BCBPointerFromhConnection;
  result = memset_0(v7, 0, sizeof(v7));
  if ( v2 && (*(_DWORD *)(v2 + 52) & 0x4000) != 0 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v2 + 48); i = (unsigned int)(i + 1) )
    {
      result = *(_QWORD **)(v2 + 8);
      v5 = result[i];
      if ( v5 )
      {
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceInfo,
            L"ProcessRemoveQuarantine: removing quarantine-session-timer");
        result = (_QWORD *)RemoveFromTimerQ(*(_DWORD *)(v5 + 64), 0, 0, 0, 4);
        if ( *(_DWORD *)(v5 + 80) )
        {
          if ( (byte_18004CF34 & 1) != 0 )
          {
            LOWORD(v6) = 0;
            FormatRRASErrorString(
              &v6,
              L"ProcessRemoveQuarantine: adding session timeout %d",
              *(unsigned int *)(v5 + 80));
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v6);
          }
          result = (_QWORD *)InsertInTimerQ(
                               *(_DWORD *)(v5 + 64),
                               *(_QWORD *)(v5 + 16),
                               0,
                               0,
                               0,
                               4,
                               *(_DWORD *)(v5 + 80));
        }
      }
    }
    *(_DWORD *)(v2 + 52) &= ~0x4000u;
  }
  return result;
}

```

## disassembly

```asm
0x1800174e0  mov     [rsp+arg_8], rbx
0x1800174e5  mov     [rsp+arg_10], rsi
0x1800174ea  push    rdi
0x1800174eb  sub     rsp, 860h
0x1800174f2  mov     rax, cs:__security_cookie
0x1800174f9  xor     rax, rsp
0x1800174fc  mov     [rsp+868h+var_18], rax
0x180017504  mov     rcx, [rcx+18h]
0x180017508  call    GetBCBPointerFromhConnection
0x18001750d  xor     ecx, ecx
0x18001750f  xor     edx, edx; Val
0x180017511  mov     [rsp+868h+var_818], ecx
0x180017515  mov     r8d, 7FCh; Size
0x18001751b  lea     rcx, [rsp+868h+var_814]; void *
0x180017520  mov     rbx, rax
0x180017523  call    memset_0
0x180017528  test    rbx, rbx
0x18001752b  jz      loc_180017616
0x180017531  test    dword ptr [rbx+34h], 4000h
0x180017538  jz      loc_180017616
0x18001753e  xor     edi, edi
0x180017540  cmp     edi, [rbx+30h]
0x180017543  jnb     loc_180017611
0x180017549  mov     rax, [rbx+8]
0x18001754d  mov     rsi, [rax+rdi*8]
0x180017551  test    rsi, rsi
0x180017554  jz      loc_18001760A
0x18001755a  test    cs:byte_18004CF34, 1
0x180017561  jz      short loc_18001757D
0x180017563  lea     r8, aProcessremoveq; "ProcessRemoveQuarantine: removing quara"...
0x18001756a  lea     rdx, RasPppTraceInfo
0x180017571  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017578  call    McTemplateU0z_EventWriteTransfer
0x18001757d  mov     ecx, [rsi+40h]
0x180017580  xor     r9d, r9d
0x180017583  xor     r8d, r8d
0x180017586  mov     [rsp+868h+var_848], 4
0x18001758e  xor     edx, edx
0x180017590  call    RemoveFromTimerQ
0x180017595  cmp     dword ptr [rsi+50h], 0
0x180017599  jbe     short loc_18001760A
0x18001759b  test    cs:byte_18004CF34, 1
0x1800175a2  jz      short loc_1800175E1
0x1800175a4  xor     eax, eax
0x1800175a6  lea     rdx, aProcessremoveq_0; "ProcessRemoveQuarantine: adding session"...
0x1800175ad  mov     word ptr [rsp+868h+var_818], ax
0x1800175b2  lea     rcx, [rsp+868h+var_818]
0x1800175b7  mov     r8d, [rsi+50h]
0x1800175bb  call    FormatRRASErrorString
0x1800175c0  test    cs:byte_18004CF34, 1
0x1800175c7  jz      short loc_1800175E1
0x1800175c9  lea     r8, [rsp+868h+var_818]
0x1800175ce  lea     rdx, RasPppTraceInfo
0x1800175d5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800175dc  call    McTemplateU0z_EventWriteTransfer
0x1800175e1  mov     eax, [rsi+50h]
0x1800175e4  xor     r9d, r9d
0x1800175e7  mov     rdx, [rsi+10h]
0x1800175eb  xor     r8d, r8d
0x1800175ee  mov     ecx, [rsi+40h]
0x1800175f1  mov     [rsp+868h+var_838], eax
0x1800175f5  mov     [rsp+868h+var_840], 4
0x1800175fd  mov     [rsp+868h+var_848], 0
0x180017605  call    InsertInTimerQ
0x18001760a  inc     edi
0x18001760c  jmp     loc_180017540
0x180017611  btr     dword ptr [rbx+34h], 0Eh
0x180017616  mov     rcx, [rsp+868h+var_18]
0x18001761e  xor     rcx, rsp; StackCookie
0x180017621  call    __security_check_cookie
0x180017626  lea     r11, [rsp+868h+var_8]
0x18001762e  mov     rbx, [r11+18h]
0x180017632  mov     rsi, [r11+20h]
0x180017636  mov     rsp, r11
0x180017639  pop     rdi
0x18001763a  retn
```
