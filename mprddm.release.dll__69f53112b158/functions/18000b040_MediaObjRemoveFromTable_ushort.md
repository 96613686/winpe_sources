# MediaObjRemoveFromTable(ushort *)

- ea: `0x18000b040`
- end: `0x18000b252`
- name: `?MediaObjRemoveFromTable@@YAXPEAG@Z`
- size: `530`
- prototype: `void __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f254`
- `0x180038560`
- `0x18003d41c`
- `0x18003d68c`
- `0x180043490`

## callees

- `0x180007c0c`
- `0x18000b040`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b0c2`
- `msvcrt!_wcsicmp` at `0x18000b0c2`
- `KERNEL32!LeaveCriticalSection` at `0x18000b21e`
- `KERNEL32!LeaveCriticalSection` at `0x18000b21e`
- `KERNEL32!EnterCriticalSection` at `0x18000b078`
- `KERNEL32!EnterCriticalSection` at `0x18000b078`

## string_xrefs

- `0x18000b103`: `Removed instance of %ws media from media table`
- `0x18000b19f`: `Removed %ws from available media table`

## pseudocode

```c
void __fastcall MediaObjRemoveFromTable(wchar_t *String2)
{
  unsigned int i; // ebx
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

  EnterCriticalSection(&stru_1800CF740);
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
        v4 = byte_1800CF404;
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString(&v13, L"Removed instance of %ws media from media table", String2);
          v4 = byte_1800CF404;
          if ( (byte_1800CF404 & 0x10) != 0 )
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
            v4 = byte_1800CF404;
          }
        }
        if ( !*(_DWORD *)(*((_QWORD *)&gblMediaTable + 1) + 40LL * i + 36) )
        {
          LODWORD(gblMediaTable) = 1;
          if ( (v4 & 0x10) != 0 )
          {
            LOWORD(v13) = 0;
            FormatRRASErrorString(&v13, L"Removed %ws from available media table", String2);
            if ( (byte_1800CF404 & 0x10) != 0 )
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
  LeaveCriticalSection(&stru_1800CF740);
}

```

## disassembly

```asm
0x18000b040  mov     [rsp-8+arg_8], rbx
0x18000b045  mov     [rsp-8+arg_10], rsi
0x18000b04a  push    rbp
0x18000b04b  push    rdi
0x18000b04c  push    r14
0x18000b04e  lea     rbp, [rsp-760h]
0x18000b056  sub     rsp, 860h
0x18000b05d  mov     rax, cs:__security_cookie
0x18000b064  xor     rax, rsp
0x18000b067  mov     [rbp+770h+var_20], rax
0x18000b06e  mov     rsi, rcx
0x18000b071  lea     rcx, stru_1800CF740; lpCriticalSection
0x18000b078  call    cs:__imp_EnterCriticalSection
0x18000b07f  nop     dword ptr [rax+rax+00h]
0x18000b084  xor     r14d, r14d
0x18000b087  lea     rcx, [rsp+870h+var_81C]; void *
0x18000b08c  xor     edx, edx; Val
0x18000b08e  mov     [rsp+870h+var_820], r14d
0x18000b093  mov     r8d, 7FCh; Size
0x18000b099  call    memset_0
0x18000b09e  cmp     dword ptr cs:gblMediaTable+4, r14d
0x18000b0a5  mov     ebx, r14d
0x18000b0a8  jbe     loc_18000B217
0x18000b0ae  mov     eax, ebx
0x18000b0b0  mov     rdx, rsi; String2
0x18000b0b3  lea     rdi, [rax+rax*4]
0x18000b0b7  mov     rax, qword ptr cs:gblMediaTable+8
0x18000b0be  lea     rcx, [rax+rdi*8]; String1
0x18000b0c2  call    cs:__imp__wcsicmp
0x18000b0c9  nop     dword ptr [rax+rax+00h]
0x18000b0ce  test    eax, eax
0x18000b0d0  jnz     loc_18000B209
0x18000b0d6  mov     rcx, qword ptr cs:gblMediaTable+8
0x18000b0dd  mov     eax, [rcx+rdi*8+24h]
0x18000b0e1  test    eax, eax
0x18000b0e3  jz      loc_18000B209
0x18000b0e9  dec     eax
0x18000b0eb  mov     [rcx+rdi*8+24h], eax
0x18000b0ef  mov     cl, cs:byte_1800CF404
0x18000b0f5  test    cl, 10h
0x18000b0f8  jz      short loc_18000B175
0x18000b0fa  mov     r8, rsi
0x18000b0fd  mov     word ptr [rsp+870h+var_820], r14w
0x18000b103  lea     rdx, aRemovedInstanc; "Removed instance of %ws media from medi"...
0x18000b10a  lea     rcx, [rsp+870h+var_820]
0x18000b10f  call    FormatRRASErrorString
0x18000b114  mov     cl, cs:byte_1800CF404
0x18000b11a  test    cl, 10h
0x18000b11d  jz      short loc_18000B175
0x18000b11f  lea     rcx, [rsp+870h+var_820]
0x18000b124  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b128  inc     rax
0x18000b12b  cmp     [rcx+rax*2], r14w
0x18000b130  jnz     short loc_18000B128
0x18000b132  lea     eax, ds:2[rax*2]
0x18000b139  mov     [rsp+870h+var_824], r14d
0x18000b13e  lea     rcx, [rsp+870h+var_820]
0x18000b143  mov     [rsp+870h+var_828], eax
0x18000b147  lea     rax, [rsp+870h+var_840]
0x18000b14c  mov     [rsp+870h+var_830], rcx
0x18000b151  mov     r9d, 2
0x18000b157  mov     [rsp+870h+var_850], rax
0x18000b15c  lea     rdx, RasDdmTraceInfo
0x18000b163  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b16a  call    McGenEventWrite_EventWriteTransfer
0x18000b16f  mov     cl, cs:byte_1800CF404
0x18000b175  mov     rax, qword ptr cs:gblMediaTable+8
0x18000b17c  cmp     [rax+rdi*8+24h], r14d
0x18000b181  jnz     loc_18000B209
0x18000b187  mov     dword ptr cs:gblMediaTable, 1
0x18000b191  test    cl, 10h
0x18000b194  jz      short loc_18000B209
0x18000b196  mov     r8, rsi
0x18000b199  mov     word ptr [rsp+870h+var_820], r14w
0x18000b19f  lea     rdx, aRemovedWsFromA; "Removed %ws from available media table"
0x18000b1a6  lea     rcx, [rsp+870h+var_820]
0x18000b1ab  call    FormatRRASErrorString
0x18000b1b0  test    cs:byte_1800CF404, 10h
0x18000b1b7  jz      short loc_18000B209
0x18000b1b9  lea     rcx, [rsp+870h+var_820]
0x18000b1be  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b1c2  inc     rax
0x18000b1c5  cmp     [rcx+rax*2], r14w
0x18000b1ca  jnz     short loc_18000B1C2
0x18000b1cc  lea     eax, ds:2[rax*2]
0x18000b1d3  mov     [rsp+870h+var_824], r14d
0x18000b1d8  lea     rcx, [rsp+870h+var_820]
0x18000b1dd  mov     [rsp+870h+var_828], eax
0x18000b1e1  lea     rax, [rsp+870h+var_840]
0x18000b1e6  mov     [rsp+870h+var_830], rcx
0x18000b1eb  mov     r9d, 2
0x18000b1f1  mov     [rsp+870h+var_850], rax
0x18000b1f6  lea     rdx, RasDdmTraceInfo
0x18000b1fd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b204  call    McGenEventWrite_EventWriteTransfer
0x18000b209  inc     ebx
0x18000b20b  cmp     ebx, dword ptr cs:gblMediaTable+4
0x18000b211  jb      loc_18000B0AE
0x18000b217  lea     rcx, stru_1800CF740; lpCriticalSection
0x18000b21e  call    cs:__imp_LeaveCriticalSection
0x18000b225  nop     dword ptr [rax+rax+00h]
0x18000b22a  mov     rcx, [rbp+770h+var_20]
0x18000b231  xor     rcx, rsp; StackCookie
0x18000b234  call    __security_check_cookie
0x18000b239  lea     r11, [rsp+870h+var_10]
0x18000b241  mov     rbx, [r11+28h]
0x18000b245  mov     rsi, [r11+30h]
0x18000b249  mov     rsp, r11
0x18000b24c  pop     r14
0x18000b24e  pop     rdi
0x18000b24f  pop     rbp
0x18000b250  retn
```
