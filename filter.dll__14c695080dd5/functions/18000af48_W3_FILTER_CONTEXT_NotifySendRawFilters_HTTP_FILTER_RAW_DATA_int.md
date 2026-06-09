# W3_FILTER_CONTEXT::NotifySendRawFilters(_HTTP_FILTER_RAW_DATA *,int *)

- ea: `0x18000af48`
- end: `0x18000b1df`
- name: `?NotifySendRawFilters@W3_FILTER_CONTEXT@@QEAAJPEAU_HTTP_FILTER_RAW_DATA@@PEAH@Z`
- size: `663`
- prototype: `__int64 __fastcall(W3_FILTER_CONTEXT *__hidden this, struct _HTTP_FILTER_RAW_DATA *, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180001d20`
- `0x180007d40`
- `0x18000c6a0`

## callees

- `0x180003f80`
- `0x180004440`
- `0x180005d50`
- `0x180006440`
- `0x18000af04`
- `0x18000af48`
- `0x18000b1e8`
- `0x18000c648`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b146`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b157`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b061`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000b061`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aff6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000aff6`
- `iisutil!PuDbgPrint` at `0x18000b121`
- `iisutil!PuDbgPrint` at `0x18000b121`

## string_xrefs

- `0x18000b11a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::NotifySendRawFilters(
        W3_FILTER_CONTEXT *this,
        struct _HTTP_FILTER_RAW_DATA *a2,
        int *a3)
{
  int v5; // r13d
  __int64 v6; // rbp
  __int64 v7; // rsi
  void **v8; // r15
  unsigned int v9; // edi
  void **v10; // r12
  BUFFER *v11; // rax
  __int64 v12; // rbp
  void *ClientContext; // rax
  const unsigned __int16 *Str; // rax
  enum SF_STATUS_TYPE v16; // r15d
  void *v17; // rsi
  signed int LastError; // eax
  __int64 result; // rax
  BUFFER *v20; // [rsp+30h] [rbp-58h]
  PVOID pvInData; // [rsp+38h] [rbp-50h] BYREF
  DWORD cbInData; // [rsp+40h] [rbp-48h]
  DWORD cbInBuffer; // [rsp+44h] [rbp-44h]
  __int64 v24; // [rsp+48h] [rbp-40h]
  void *v25; // [rsp+98h] [rbp+10h]
  void *v27; // [rsp+A8h] [rbp+20h]

  v24 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v5 = *((_DWORD *)this + 70);
  v6 = *((_QWORD *)this + 14);
  pvInData = a2->pvInData;
  cbInData = a2->cbInData;
  cbInBuffer = a2->cbInBuffer;
  *a3 = 0;
  if ( v5 == -1 )
  {
    v7 = (unsigned int)(*(_DWORD *)(v6 + 16) - 1);
  }
  else
  {
    if ( !v5 )
      return 0;
    v7 = (unsigned int)(v5 - 1);
  }
  v8 = (void **)((char *)this + 64);
  v9 = 0;
  v25 = (void *)*((_QWORD *)this + 8);
  v10 = (void **)((char *)this + 64);
  W3_FILTER_CONTEXT::RaiseEventPreCall(this, 0x400u, 0, 0);
  v11 = (BUFFER *)(v6 + 24);
  v20 = (BUFFER *)(v6 + 24);
  while ( 1 )
  {
    v12 = *((_QWORD *)BUFFER::QueryPtr(v11) + v7);
    if ( !(*((_DWORD *)this + 64)
         ? (unsigned int)W3_FILTER_CONTEXT::IsDisableNotificationNeeded(this, v7, 0x400u) == 0
         : (*(_DWORD *)((*((_DWORD *)this + 15) != 0 ? 4 : 0) + v12 + 60) & 0x400) == 0) )
      break;
LABEL_26:
    if ( !(_DWORD)v7 )
      goto LABEL_33;
    v11 = v20;
    v7 = (unsigned int)(v7 - 1);
  }
  if ( *(_DWORD *)(v12 + 128) )
    ClientContext = W3_FILTER_CONTEXT::QueryClientContext(this, (void *)v12);
  else
    ClientContext = 0;
  *v8 = ClientContext;
  *((_DWORD *)this + 70) = v7;
  v27 = ClientContext;
  Str = STRU::QueryStr((STRU *)(v12 + 72));
  W3_FILTER_CONTEXT::TraceFilterStart(this, Str);
  v16 = (*(unsigned int (__fastcall **)(char *, __int64, PVOID *))(v12 + 32))((char *)this + 40, 1024, &pvInData);
  W3_FILTER_CONTEXT::TraceFilterEnd(this, v16);
  if ( v27 != *v10 || *(_DWORD *)(v12 + 128) )
  {
    W3_FILTER_CONTEXT::SetClientContext(this, (void *)v12, *v10);
    *(_DWORD *)(v12 + 128) = 1;
  }
  switch ( v16 )
  {
    case SF_STATUS_REQ_FINISHED:
    case SF_STATUS_REQ_FINISHED_KEEP_CONN:
      *a3 = 1;
LABEL_33:
      v17 = v25;
      goto LABEL_34;
    case SF_STATUS_REQ_NEXT_NOTIFICATION:
LABEL_25:
      v8 = v10;
      goto LABEL_26;
    case SF_STATUS_REQ_HANDLED_NOTIFICATION:
      goto LABEL_33;
  }
  if ( v16 != SF_STATUS_REQ_ERROR )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
        1182,
        "W3_FILTER_CONTEXT::NotifySendRawFilters",
        "Unknown status code from filter %d\n",
        v16);
    goto LABEL_25;
  }
  v17 = v25;
  *v10 = v25;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v9 = -2147024883;
  }
LABEL_34:
  W3_FILTER_CONTEXT::RaiseEventPostCall(this, 0x400u, 0, 0);
  result = v9;
  a2->pvInData = pvInData;
  a2->cbInData = cbInData;
  a2->cbInBuffer = cbInBuffer;
  *v10 = v17;
  *((_DWORD *)this + 70) = v5;
  return result;
}

```

## disassembly

```asm
0x18000af48  mov     r11, rsp
0x18000af4b  mov     [r11+8], rbx
0x18000af4f  mov     [r11+18h], r8
0x18000af53  push    rbp
0x18000af54  push    rsi
0x18000af55  push    rdi
0x18000af56  push    r12
0x18000af58  push    r13
0x18000af5a  push    r14
0x18000af5c  push    r15
0x18000af5e  sub     rsp, 50h
0x18000af62  mov     qword ptr [r11-40h], 0
0x18000af6a  mov     rax, r8
0x18000af6d  mov     r14, rdx
0x18000af70  mov     rbx, rcx
0x18000af73  test    rdx, rdx
0x18000af76  jz      loc_18000B1C2
0x18000af7c  test    rax, rax
0x18000af7f  jz      loc_18000B1C2
0x18000af85  mov     rax, [rdx]
0x18000af88  mov     r13d, [rcx+118h]
0x18000af8f  mov     rbp, [rcx+70h]
0x18000af93  mov     [r11-50h], rax
0x18000af97  mov     eax, [rdx+8]
0x18000af9a  mov     [rsp+88h+var_48], eax
0x18000af9e  mov     eax, [rdx+0Ch]
0x18000afa1  mov     [rsp+88h+var_44], eax
0x18000afa5  mov     dword ptr [r8], 0
0x18000afac  cmp     r13d, 0FFFFFFFFh
0x18000afb0  jnz     short loc_18000AFB9
0x18000afb2  mov     esi, [rbp+10h]
0x18000afb5  dec     esi
0x18000afb7  jmp     short loc_18000AFC6
0x18000afb9  test    r13d, r13d
0x18000afbc  jz      loc_18000B1BE
0x18000afc2  lea     esi, [r13-1]
0x18000afc6  lea     r15, [rcx+40h]
0x18000afca  xor     edi, edi
0x18000afcc  mov     rax, [r15]
0x18000afcf  xor     r9d, r9d; struct STRA *
0x18000afd2  xor     r8d, r8d; void *
0x18000afd5  mov     [rsp+88h+arg_8], rax
0x18000afdd  mov     edx, 400h; unsigned int
0x18000afe2  mov     r12, r15
0x18000afe5  call    ?RaiseEventPreCall@W3_FILTER_CONTEXT@@AEAAJKPEAXPEAVSTRA@@@Z; W3_FILTER_CONTEXT::RaiseEventPreCall(ulong,void *,STRA *)
0x18000afea  lea     rax, [rbp+18h]
0x18000afee  mov     [rsp+88h+var_58], rax
0x18000aff3  mov     rcx, rax
0x18000aff6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000affc  mov     rbp, [rax+rsi*8]
0x18000b000  cmp     [rbx+100h], edi
0x18000b006  jnz     short loc_18000B01D
0x18000b008  mov     eax, [rbx+3Ch]
0x18000b00b  neg     eax
0x18000b00d  sbb     rcx, rcx
0x18000b010  and     ecx, 4
0x18000b013  test    dword ptr [rcx+rbp+3Ch], 400h
0x18000b01b  jmp     short loc_18000B02F
0x18000b01d  mov     r8d, 400h; unsigned int
0x18000b023  mov     edx, esi; unsigned int
0x18000b025  mov     rcx, rbx; this
0x18000b028  call    ?IsDisableNotificationNeeded@W3_FILTER_CONTEXT@@QEAAHKK@Z; W3_FILTER_CONTEXT::IsDisableNotificationNeeded(ulong,ulong)
0x18000b02d  test    eax, eax
0x18000b02f  jz      loc_18000B12A
0x18000b035  cmp     [rbp+80h], edi
0x18000b03b  jz      short loc_18000B04A
0x18000b03d  mov     rdx, rbp; void *
0x18000b040  mov     rcx, rbx; this
0x18000b043  call    ?QueryClientContext@W3_FILTER_CONTEXT@@QEAAPEAXPEAX@Z; W3_FILTER_CONTEXT::QueryClientContext(void *)
0x18000b048  jmp     short loc_18000B04C
0x18000b04a  xor     eax, eax
0x18000b04c  mov     [r15], rax
0x18000b04f  lea     rcx, [rbp+48h]
0x18000b053  mov     [rbx+118h], esi
0x18000b059  mov     [rsp+88h+arg_18], rax
0x18000b061  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000b067  mov     rdx, rax; unsigned __int16 *
0x18000b06a  mov     rcx, rbx; this
0x18000b06d  call    ?TraceFilterStart@W3_FILTER_CONTEXT@@AEAAXPEBG@Z; W3_FILTER_CONTEXT::TraceFilterStart(ushort const *)
0x18000b072  mov     rax, [rbp+20h]
0x18000b076  lea     rcx, [rbx+28h]
0x18000b07a  lea     r8, [rsp+88h+var_50]
0x18000b07f  mov     edx, 400h
0x18000b084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b089  mov     edx, eax; enum SF_STATUS_TYPE
0x18000b08b  mov     rcx, rbx; this
0x18000b08e  mov     r15d, eax
0x18000b091  call    ?TraceFilterEnd@W3_FILTER_CONTEXT@@AEAAXW4SF_STATUS_TYPE@@@Z; W3_FILTER_CONTEXT::TraceFilterEnd(SF_STATUS_TYPE)
0x18000b096  mov     r8, [r12]; void *
0x18000b09a  cmp     [rsp+88h+arg_18], r8
0x18000b0a2  jnz     short loc_18000B0AC
0x18000b0a4  cmp     [rbp+80h], edi
0x18000b0aa  jz      short loc_18000B0C1
0x18000b0ac  mov     rdx, rbp; void *
0x18000b0af  mov     rcx, rbx; this
0x18000b0b2  call    ?SetClientContext@W3_FILTER_CONTEXT@@QEAAXPEAX0@Z; W3_FILTER_CONTEXT::SetClientContext(void *,void *)
0x18000b0b7  mov     dword ptr [rbp+80h], 1
0x18000b0c1  mov     ecx, r15d
0x18000b0c4  sub     ecx, 8000000h
0x18000b0ca  jz      loc_18000B16E
0x18000b0d0  sub     ecx, 1
0x18000b0d3  jz      loc_18000B16E
0x18000b0d9  sub     ecx, 1
0x18000b0dc  jz      short loc_18000B127
0x18000b0de  sub     ecx, 1
0x18000b0e1  jz      loc_18000B17C
0x18000b0e7  cmp     ecx, 1
0x18000b0ea  jz      short loc_18000B13A
0x18000b0ec  test    cs:g_dwDebugFlags, 3
0x18000b0f3  jz      short loc_18000B127
0x18000b0f5  mov     rcx, cs:g_pDebug
0x18000b0fc  lea     rax, aUnknownStatusC; "Unknown status code from filter %d\n"
0x18000b103  mov     [rsp+88h+var_60], r15d
0x18000b108  lea     r9, aW3FilterContex_0; "W3_FILTER_CONTEXT::NotifySendRawFilters"
0x18000b10f  mov     r8d, 49Eh
0x18000b115  mov     [rsp+88h+var_68], rax
0x18000b11a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000b121  call    cs:__imp_PuDbgPrint
0x18000b127  mov     r15, r12
0x18000b12a  test    esi, esi
0x18000b12c  jz      short loc_18000B17C
0x18000b12e  mov     rax, [rsp+88h+var_58]
0x18000b133  dec     esi
0x18000b135  jmp     loc_18000AFF3
0x18000b13a  mov     rsi, [rsp+88h+arg_8]
0x18000b142  mov     [r12], rsi
0x18000b146  call    cs:__imp_GetLastError
0x18000b14c  test    eax, eax
0x18000b14e  jnz     short loc_18000B157
0x18000b150  mov     edi, 8007000Dh
0x18000b155  jmp     short loc_18000B184
0x18000b157  call    cs:__imp_GetLastError
0x18000b15d  mov     edi, eax
0x18000b15f  test    eax, eax
0x18000b161  jle     short loc_18000B184
0x18000b163  movzx   edi, ax
0x18000b166  or      edi, 80070000h
0x18000b16c  jmp     short loc_18000B184
0x18000b16e  mov     rax, [rsp+88h+arg_10]
0x18000b176  mov     dword ptr [rax], 1
0x18000b17c  mov     rsi, [rsp+88h+arg_8]
0x18000b184  xor     r9d, r9d; struct STRA *
0x18000b187  xor     r8d, r8d; void *
0x18000b18a  mov     edx, 400h; unsigned int
0x18000b18f  mov     rcx, rbx; this
0x18000b192  call    ?RaiseEventPostCall@W3_FILTER_CONTEXT@@AEAAJKPEAXPEAVSTRA@@@Z; W3_FILTER_CONTEXT::RaiseEventPostCall(ulong,void *,STRA *)
0x18000b197  mov     rcx, [rsp+88h+var_50]
0x18000b19c  mov     eax, edi
0x18000b19e  mov     [r14], rcx
0x18000b1a1  mov     ecx, [rsp+88h+var_48]
0x18000b1a5  mov     [r14+8], ecx
0x18000b1a9  mov     ecx, [rsp+88h+var_44]
0x18000b1ad  mov     [r14+0Ch], ecx
0x18000b1b1  mov     [r12], rsi
0x18000b1b5  mov     [rbx+118h], r13d
0x18000b1bc  jmp     short loc_18000B1C7
0x18000b1be  xor     eax, eax
0x18000b1c0  jmp     short loc_18000B1C7
0x18000b1c2  mov     eax, 80070057h
0x18000b1c7  mov     rbx, [rsp+88h+arg_0]
0x18000b1cf  add     rsp, 50h
0x18000b1d3  pop     r15
0x18000b1d5  pop     r14
0x18000b1d7  pop     r13
0x18000b1d9  pop     r12
0x18000b1db  pop     rdi
0x18000b1dc  pop     rsi
0x18000b1dd  pop     rbp
0x18000b1de  retn
```
