# MediaObjRemoveFromTable(ushort *)

- ea: `0x18000adb4`
- end: `0x18000afb3`
- name: `?MediaObjRemoveFromTable@@YAXPEAG@Z`
- size: `511`
- prototype: `void __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000ed5c`
- `0x180036aa0`
- `0x18003ba98`
- `0x18003bd08`
- `0x180041cb0`

## callees

- `0x180007b7c`
- `0x18000adb4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ae30`
- `msvcrt!_wcsicmp` at `0x18000ae30`
- `KERNEL32!LeaveCriticalSection` at `0x18000af86`
- `KERNEL32!LeaveCriticalSection` at `0x18000af86`
- `KERNEL32!EnterCriticalSection` at `0x18000adec`
- `KERNEL32!EnterCriticalSection` at `0x18000adec`

## string_xrefs

- `0x18000ae6b`: `Removed instance of %ws media from media table`
- `0x18000af07`: `Removed %ws from available media table`

## pseudocode

```c
void __fastcall MediaObjRemoveFromTable(wchar_t *String2)
{
  unsigned int i; // edi
  int v3; // eax
  char v4; // cl
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-D0h] BYREF
  int *v10; // [rsp+40h] [rbp-C0h]
  int v11; // [rsp+48h] [rbp-B8h]
  int v12; // [rsp+4Ch] [rbp-B4h]
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[2044]; // [rsp+54h] [rbp-ACh] BYREF

  EnterCriticalSection(&stru_1800C8740);
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  for ( i = 0; i < DWORD1(gblMediaTable); ++i )
  {
    if ( !_wcsicmp((const wchar_t *)(*((_QWORD *)&gblMediaTable + 1) + 40LL * i), String2) )
    {
      v3 = *(_DWORD *)(*((_QWORD *)&gblMediaTable + 1) + 40LL * i + 36);
      if ( v3 )
      {
        *(_DWORD *)(*((_QWORD *)&gblMediaTable + 1) + 40LL * i + 36) = v3 - 1;
        v4 = byte_1800C8404;
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString(&v13, L"Removed instance of %ws media from media table", String2);
          v4 = byte_1800C8404;
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v6 = -1;
            do
              ++v6;
            while ( *(_WORD *)&v14[2 * v6 - 4] );
            v12 = 0;
            v11 = 2 * v6 + 2;
            v10 = &v13;
            McGenEventWrite_EventWriteTransfer(
              (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
              v5,
              2u,
              &v9);
            v4 = byte_1800C8404;
          }
        }
        if ( !*(_DWORD *)(*((_QWORD *)&gblMediaTable + 1) + 40LL * i + 36) )
        {
          LODWORD(gblMediaTable) = 1;
          if ( (v4 & 0x10) != 0 )
          {
            LOWORD(v13) = 0;
            FormatRRASErrorString(&v13, L"Removed %ws from available media table", String2);
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              v8 = -1;
              do
                ++v8;
              while ( *(_WORD *)&v14[2 * v8 - 4] );
              v12 = 0;
              v11 = 2 * v8 + 2;
              v10 = &v13;
              McGenEventWrite_EventWriteTransfer(
                (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
                v7,
                2u,
                &v9);
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection(&stru_1800C8740);
}

```

## disassembly

```asm
0x18000adb4  mov     [rsp-8+arg_8], rbx
0x18000adb9  mov     [rsp-8+arg_10], rsi
0x18000adbe  push    rbp
0x18000adbf  push    rdi
0x18000adc0  push    r14
0x18000adc2  lea     rbp, [rsp-760h]
0x18000adca  sub     rsp, 860h
0x18000add1  mov     rax, cs:__security_cookie
0x18000add8  xor     rax, rsp
0x18000addb  mov     [rbp+770h+var_20], rax
0x18000ade2  mov     rsi, rcx
0x18000ade5  lea     rcx, stru_1800C8740; lpCriticalSection
0x18000adec  call    cs:__imp_EnterCriticalSection
0x18000adf2  xor     r14d, r14d
0x18000adf5  lea     rcx, [rsp+870h+var_81C]; void *
0x18000adfa  xor     edx, edx; Val
0x18000adfc  mov     [rsp+870h+var_820], r14d
0x18000ae01  mov     r8d, 7FCh; Size
0x18000ae07  call    memset_0
0x18000ae0c  cmp     dword ptr cs:gblMediaTable+4, r14d
0x18000ae13  mov     edi, r14d
0x18000ae16  jbe     loc_18000AF7F
0x18000ae1c  mov     eax, edi
0x18000ae1e  mov     rdx, rsi; String2
0x18000ae21  lea     rbx, [rax+rax*4]
0x18000ae25  mov     rax, qword ptr cs:gblMediaTable+8
0x18000ae2c  lea     rcx, [rax+rbx*8]; String1
0x18000ae30  call    cs:__imp__wcsicmp
0x18000ae36  test    eax, eax
0x18000ae38  jnz     loc_18000AF71
0x18000ae3e  mov     rcx, qword ptr cs:gblMediaTable+8
0x18000ae45  mov     eax, [rcx+rbx*8+24h]
0x18000ae49  test    eax, eax
0x18000ae4b  jz      loc_18000AF71
0x18000ae51  dec     eax
0x18000ae53  mov     [rcx+rbx*8+24h], eax
0x18000ae57  mov     cl, cs:byte_1800C8404
0x18000ae5d  test    cl, 10h
0x18000ae60  jz      short loc_18000AEDD
0x18000ae62  mov     r8, rsi
0x18000ae65  mov     word ptr [rsp+870h+var_820], r14w
0x18000ae6b  lea     rdx, aRemovedInstanc; "Removed instance of %ws media from medi"...
0x18000ae72  lea     rcx, [rsp+870h+var_820]
0x18000ae77  call    FormatRRASErrorString
0x18000ae7c  mov     cl, cs:byte_1800C8404
0x18000ae82  test    cl, 10h
0x18000ae85  jz      short loc_18000AEDD
0x18000ae87  lea     rcx, [rsp+870h+var_820]
0x18000ae8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae90  inc     rax
0x18000ae93  cmp     [rcx+rax*2], r14w
0x18000ae98  jnz     short loc_18000AE90
0x18000ae9a  lea     eax, ds:2[rax*2]
0x18000aea1  mov     [rsp+870h+var_824], r14d
0x18000aea6  lea     rcx, [rsp+870h+var_820]
0x18000aeab  mov     [rsp+870h+var_828], eax
0x18000aeaf  lea     rax, [rsp+870h+var_840]
0x18000aeb4  mov     [rsp+870h+var_830], rcx
0x18000aeb9  mov     r9d, 2
0x18000aebf  mov     [rsp+870h+var_850], rax
0x18000aec4  lea     rdx, RasDdmTraceInfo
0x18000aecb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aed2  call    McGenEventWrite_EventWriteTransfer
0x18000aed7  mov     cl, cs:byte_1800C8404
0x18000aedd  mov     rax, qword ptr cs:gblMediaTable+8
0x18000aee4  cmp     [rax+rbx*8+24h], r14d
0x18000aee9  jnz     loc_18000AF71
0x18000aeef  mov     dword ptr cs:gblMediaTable, 1
0x18000aef9  test    cl, 10h
0x18000aefc  jz      short loc_18000AF71
0x18000aefe  mov     r8, rsi
0x18000af01  mov     word ptr [rsp+870h+var_820], r14w
0x18000af07  lea     rdx, aRemovedWsFromA; "Removed %ws from available media table"
0x18000af0e  lea     rcx, [rsp+870h+var_820]
0x18000af13  call    FormatRRASErrorString
0x18000af18  test    cs:byte_1800C8404, 10h
0x18000af1f  jz      short loc_18000AF71
0x18000af21  lea     rcx, [rsp+870h+var_820]
0x18000af26  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000af2a  inc     rax
0x18000af2d  cmp     [rcx+rax*2], r14w
0x18000af32  jnz     short loc_18000AF2A
0x18000af34  lea     eax, ds:2[rax*2]
0x18000af3b  mov     [rsp+870h+var_824], r14d
0x18000af40  lea     rcx, [rsp+870h+var_820]
0x18000af45  mov     [rsp+870h+var_828], eax
0x18000af49  lea     rax, [rsp+870h+var_840]
0x18000af4e  mov     [rsp+870h+var_830], rcx
0x18000af53  mov     r9d, 2
0x18000af59  mov     [rsp+870h+var_850], rax
0x18000af5e  lea     rdx, RasDdmTraceInfo
0x18000af65  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000af6c  call    McGenEventWrite_EventWriteTransfer
0x18000af71  inc     edi
0x18000af73  cmp     edi, dword ptr cs:gblMediaTable+4
0x18000af79  jb      loc_18000AE1C
0x18000af7f  lea     rcx, stru_1800C8740; lpCriticalSection
0x18000af86  call    cs:__imp_LeaveCriticalSection
0x18000af8c  mov     rcx, [rbp+770h+var_20]
0x18000af93  xor     rcx, rsp; StackCookie
0x18000af96  call    __security_check_cookie
0x18000af9b  lea     r11, [rsp+870h+var_10]
0x18000afa3  mov     rbx, [r11+28h]
0x18000afa7  mov     rsi, [r11+30h]
0x18000afab  mov     rsp, r11
0x18000afae  pop     r14
0x18000afb0  pop     rdi
0x18000afb1  pop     rbp
0x18000afb2  retn
```
