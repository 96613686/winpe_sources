# ProcessRemoveQuarantine

- ea: `0x180017cf0`
- end: `0x180017e4c`
- name: `ProcessRemoveQuarantine`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000f780`
- `0x18000f984`
- `0x180010ed0`
- `0x180017cf0`
- `0x18002b0dc`

## string_xrefs

- `0x180017d73`: `ProcessRemoveQuarantine: removing quarantine-session-timer`
- `0x180017db6`: `ProcessRemoveQuarantine: adding session timeout %d`

## pseudocode

```c
int __fastcall ProcessRemoveQuarantine(__int64 a1)
{
  _QWORD *BCBPointerFromhConnection; // rax
  _QWORD *v2; // rbx
  __int64 v3; // rax
  __int64 i; // rdi
  __int64 v5; // rsi
  int v7; // [rsp+50h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+54h] [rbp-814h] BYREF

  BCBPointerFromhConnection = GetBCBPointerFromhConnection(*(_QWORD *)(a1 + 24));
  v7 = 0;
  v2 = BCBPointerFromhConnection;
  LODWORD(v3) = (unsigned int)memset_0(v8, 0, sizeof(v8));
  if ( v2 && (*((_DWORD *)v2 + 13) & 0x4000) != 0 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 12); i = (unsigned int)(i + 1) )
    {
      v3 = v2[1];
      v5 = *(_QWORD *)(v3 + 8 * i);
      if ( v5 )
      {
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceInfo,
            L"ProcessRemoveQuarantine: removing quarantine-session-timer");
        LODWORD(v3) = RemoveFromTimerQ(*(_DWORD *)(v5 + 64), 0, 0, 0, 4);
        if ( *(_DWORD *)(v5 + 80) )
        {
          if ( (byte_18004DF34 & 1) != 0 )
          {
            LOWORD(v7) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v7,
              L"ProcessRemoveQuarantine: adding session timeout %d",
              *(unsigned int *)(v5 + 80));
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v7);
          }
          LODWORD(v3) = InsertInTimerQ(*(_DWORD *)(v5 + 64), *(_QWORD *)(v5 + 16), 0, 0, 0, 4, *(_DWORD *)(v5 + 80));
        }
      }
    }
    *((_DWORD *)v2 + 13) &= ~0x4000u;
  }
  return v3;
}

```

## disassembly

```asm
0x180017cf0  mov     [rsp+arg_8], rbx
0x180017cf5  mov     [rsp+arg_10], rsi
0x180017cfa  push    rdi
0x180017cfb  sub     rsp, 860h
0x180017d02  mov     rax, cs:__security_cookie
0x180017d09  xor     rax, rsp
0x180017d0c  mov     [rsp+868h+var_18], rax
0x180017d14  mov     rcx, [rcx+18h]
0x180017d18  call    GetBCBPointerFromhConnection
0x180017d1d  xor     ecx, ecx
0x180017d1f  xor     edx, edx; Val
0x180017d21  mov     [rsp+868h+var_818], ecx
0x180017d25  mov     r8d, 7FCh; Size
0x180017d2b  lea     rcx, [rsp+868h+var_814]; void *
0x180017d30  mov     rbx, rax
0x180017d33  call    memset_0
0x180017d38  test    rbx, rbx
0x180017d3b  jz      loc_180017E26
0x180017d41  test    dword ptr [rbx+34h], 4000h
0x180017d48  jz      loc_180017E26
0x180017d4e  xor     edi, edi
0x180017d50  cmp     edi, [rbx+30h]
0x180017d53  jnb     loc_180017E21
0x180017d59  mov     rax, [rbx+8]
0x180017d5d  mov     rsi, [rax+rdi*8]
0x180017d61  test    rsi, rsi
0x180017d64  jz      loc_180017E1A
0x180017d6a  test    cs:byte_18004DF34, 1
0x180017d71  jz      short loc_180017D8D
0x180017d73  lea     r8, aProcessremoveq; "ProcessRemoveQuarantine: removing quara"...
0x180017d7a  lea     rdx, RasPppTraceInfo
0x180017d81  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017d88  call    McTemplateU0z_EventWriteTransfer
0x180017d8d  mov     ecx, [rsi+40h]
0x180017d90  xor     r9d, r9d
0x180017d93  xor     r8d, r8d
0x180017d96  mov     [rsp+868h+var_848], 4
0x180017d9e  xor     edx, edx
0x180017da0  call    RemoveFromTimerQ
0x180017da5  cmp     dword ptr [rsi+50h], 0
0x180017da9  jbe     short loc_180017E1A
0x180017dab  test    cs:byte_18004DF34, 1
0x180017db2  jz      short loc_180017DF1
0x180017db4  xor     eax, eax
0x180017db6  lea     rdx, aProcessremoveq_0; "ProcessRemoveQuarantine: adding session"...
0x180017dbd  mov     word ptr [rsp+868h+var_818], ax
0x180017dc2  lea     rcx, [rsp+868h+var_818]
0x180017dc7  mov     r8d, [rsi+50h]
0x180017dcb  call    FormatRRASErrorString
0x180017dd0  test    cs:byte_18004DF34, 1
0x180017dd7  jz      short loc_180017DF1
0x180017dd9  lea     r8, [rsp+868h+var_818]
0x180017dde  lea     rdx, RasPppTraceInfo
0x180017de5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017dec  call    McTemplateU0z_EventWriteTransfer
0x180017df1  mov     eax, [rsi+50h]
0x180017df4  xor     r9d, r9d
0x180017df7  mov     rdx, [rsi+10h]
0x180017dfb  xor     r8d, r8d
0x180017dfe  mov     ecx, [rsi+40h]
0x180017e01  mov     [rsp+868h+var_838], eax
0x180017e05  mov     [rsp+868h+var_840], 4
0x180017e0d  mov     [rsp+868h+var_848], 0
0x180017e15  call    InsertInTimerQ
0x180017e1a  inc     edi
0x180017e1c  jmp     loc_180017D50
0x180017e21  btr     dword ptr [rbx+34h], 0Eh
0x180017e26  mov     rcx, [rsp+868h+var_18]
0x180017e2e  xor     rcx, rsp; StackCookie
0x180017e31  call    __security_check_cookie
0x180017e36  lea     r11, [rsp+868h+var_8]
0x180017e3e  mov     rbx, [r11+18h]
0x180017e42  mov     rsi, [r11+20h]
0x180017e46  mov     rsp, r11
0x180017e49  pop     rdi
0x180017e4a  retn
```
