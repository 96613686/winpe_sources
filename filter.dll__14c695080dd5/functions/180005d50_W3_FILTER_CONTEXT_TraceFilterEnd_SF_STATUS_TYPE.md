# W3_FILTER_CONTEXT::TraceFilterEnd(SF_STATUS_TYPE)

- ea: `0x180005d50`
- end: `0x180005f05`
- name: `?TraceFilterEnd@W3_FILTER_CONTEXT@@AEAAXW4SF_STATUS_TYPE@@@Z`
- size: `437`
- prototype: `void __fastcall(W3_FILTER_CONTEXT *__hidden this, enum SF_STATUS_TYPE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000af48`

## callees

- `0x180005d50`
- `0x18000d010`

## string_xrefs

- `0x180005ed5`: `SF_STATUS_REQ_READ_NEXT`

## pseudocode

```c
void __fastcall W3_FILTER_CONTEXT::TraceFilterEnd(W3_FILTER_CONTEXT *this, enum SF_STATUS_TYPE a2)
{
  int (__fastcall ***v4)(_QWORD, GUID **); // rax
  int (__fastcall **v5)(_QWORD, GUID **); // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  GUID *v9; // [rsp+20h] [rbp-99h] BYREF
  __int128 v10; // [rsp+28h] [rbp-91h]
  _QWORD v11[6]; // [rsp+40h] [rbp-79h] BYREF
  __int128 v12; // [rsp+70h] [rbp-49h]
  int v13; // [rsp+80h] [rbp-39h]
  int v14; // [rsp+84h] [rbp-35h]
  __int64 v15; // [rsp+88h] [rbp-31h]
  const wchar_t **v16; // [rsp+90h] [rbp-29h]
  const wchar_t *v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A8h] [rbp-11h]
  __int64 v19; // [rsp+B0h] [rbp-9h]
  int v20; // [rsp+B8h] [rbp-1h]
  __int64 v21; // [rsp+C0h] [rbp+7h]
  const wchar_t *v22; // [rsp+C8h] [rbp+Fh]
  int v23; // [rsp+D0h] [rbp+17h]
  enum SF_STATUS_TYPE *v24; // [rsp+D8h] [rbp+1Fh]
  int v25; // [rsp+E0h] [rbp+27h]
  const wchar_t *v26; // [rsp+E8h] [rbp+2Fh]
  enum SF_STATUS_TYPE v27; // [rsp+120h] [rbp+67h] BYREF

  v4 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 272LL))(*((_QWORD *)this + 3));
  v9 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
  v5 = *v4;
  v10 = 0;
  if ( (*v5)(v4, &v9) >= 0 && DWORD2(v10) && ((_DWORD)v10 == 8 || (v10 & 8) != 0) )
  {
    v6 = *((_QWORD *)this + 3);
    v27 = a2;
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 272LL))(v6);
    v11[1] = 8;
    v11[3] = 2;
    v15 = 2;
    v11[2] = &`IISFilterEvents::GetAreaGuid'::`2'::AreaGuid;
    v11[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v11[4] = L"FILTER_END";
    v17 = L"ContextId";
    v22 = L"NotificationStatus";
    v24 = &v27;
    v11[5] = 1;
    v12 = 0;
    v13 = 0;
    v14 = 1;
    v18 = 72;
    v19 = 0;
    v20 = 16;
    v21 = 0;
    v23 = 19;
    v25 = 4;
    switch ( v27 )
    {
      case SF_STATUS_REQ_FINISHED:
        v8 = L"SF_STATUS_REQ_FINISHED";
        break;
      case SF_STATUS_REQ_FINISHED_KEEP_CONN:
        v8 = L"SF_STATUS_REQ_FINISHED_KEEP_CONN";
        break;
      case SF_STATUS_REQ_NEXT_NOTIFICATION:
        v8 = L"SF_STATUS_REQ_NEXT_NOTIFICATION";
        break;
      case SF_STATUS_REQ_HANDLED_NOTIFICATION:
        v8 = L"SF_STATUS_REQ_HANDLED_NOTIFICATION";
        break;
      case SF_STATUS_REQ_ERROR:
        v8 = L"SF_STATUS_REQ_ERROR";
        break;
      case SF_STATUS_REQ_READ_NEXT:
        v8 = L"SF_STATUS_REQ_READ_NEXT";
        break;
      default:
        v8 = 0;
        break;
    }
    v26 = v8;
    v16 = &v17;
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 16LL))(v7, v11);
  }
}

```

## disassembly

```asm
0x180005d50  push    rbp
0x180005d52  push    rbx
0x180005d53  push    rsi
0x180005d54  push    rdi
0x180005d55  lea     rbp, [rsp-3Fh]
0x180005d5a  sub     rsp, 0F8h
0x180005d61  mov     rbx, rcx
0x180005d64  mov     edi, edx
0x180005d66  mov     rcx, [rcx+18h]
0x180005d6a  mov     rax, [rcx]
0x180005d6d  mov     rax, [rax+110h]
0x180005d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d79  mov     r8, rax
0x180005d7c  lea     rsi, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180005d83  xorps   xmm0, xmm0
0x180005d86  mov     [rsp+110h+var_F0], rsi
0x180005d8b  lea     rdx, [rsp+110h+var_F0]
0x180005d90  mov     rcx, [rax]
0x180005d93  movdqu  [rsp+110h+var_E8], xmm0
0x180005d99  mov     rax, [rcx]
0x180005d9c  mov     rcx, r8
0x180005d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da4  test    eax, eax
0x180005da6  js      short loc_180005DB3
0x180005da8  cmp     dword ptr [rsp+110h+var_E8+8], 0
0x180005dad  jnz     loc_180005E9A
0x180005db3  add     rsp, 0F8h
0x180005dba  pop     rdi
0x180005dbb  pop     rsi
0x180005dbc  pop     rbx
0x180005dbd  pop     rbp
0x180005dbe  retn
0x180005dbf  mov     rcx, [rbx+18h]
0x180005dc3  mov     [rbp+57h+arg_0], edi
0x180005dc6  mov     rax, [rcx]
0x180005dc9  mov     rax, [rax+110h]
0x180005dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd5  mov     rcx, rax
0x180005dd8  mov     [rbp+57h+var_C8], 8
0x180005de0  xor     edx, edx
0x180005de2  mov     [rbp+57h+var_B8], 2
0x180005dea  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISFilterEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISFilterEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180005df1  mov     [rbp+57h+var_88], 2
0x180005df9  mov     [rbp+57h+var_C0], rax
0x180005dfd  xorps   xmm0, xmm0
0x180005e00  lea     rax, aFilterEnd; "FILTER_END"
0x180005e07  mov     [rbp+57h+var_D0], rsi
0x180005e0b  mov     [rbp+57h+var_B0], rax
0x180005e0f  lea     rax, aContextid; "ContextId"
0x180005e16  mov     [rbp+57h+var_70], rax
0x180005e1a  lea     rax, aNotificationst; "NotificationStatus"
0x180005e21  mov     [rbp+57h+var_48], rax
0x180005e25  lea     rax, [rbp+57h+arg_0]
0x180005e29  mov     [rbp+57h+var_38], rax
0x180005e2d  mov     eax, [rbp+57h+arg_0]
0x180005e30  mov     [rbp+57h+var_A8], 1
0x180005e38  movdqa  [rbp+57h+var_A0], xmm0
0x180005e3d  mov     [rbp+57h+var_90], edx
0x180005e40  mov     [rbp+57h+var_8C], 1
0x180005e47  mov     [rbp+57h+var_68], 48h ; 'H'
0x180005e4e  mov     [rbp+57h+var_60], rdx
0x180005e52  mov     [rbp+57h+var_58], 10h
0x180005e59  mov     [rbp+57h+var_50], rdx
0x180005e5d  mov     [rbp+57h+var_40], 13h
0x180005e64  mov     [rbp+57h+var_30], 4
0x180005e6b  cmp     eax, 8000000h
0x180005e70  jnz     short loc_180005EB5
0x180005e72  lea     rax, aSfStatusReqFin_0; "SF_STATUS_REQ_FINISHED"
0x180005e79  mov     [rbp+57h+var_28], rax
0x180005e7d  lea     rdx, [rbp+57h+var_D0]
0x180005e81  lea     rax, [rbp+57h+var_70]
0x180005e85  mov     [rbp+57h+var_80], rax
0x180005e89  mov     rax, [rcx]
0x180005e8c  mov     rax, [rax+10h]
0x180005e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e95  jmp     loc_180005DB3
0x180005e9a  mov     rax, qword ptr [rsp+110h+var_E8]
0x180005e9f  cmp     eax, 8
0x180005ea2  jz      loc_180005DBF
0x180005ea8  test    al, 8
0x180005eaa  jz      loc_180005DB3
0x180005eb0  jmp     loc_180005DBF
0x180005eb5  sub     eax, 8000001h
0x180005eba  jz      short loc_180005EF9
0x180005ebc  sub     eax, 1
0x180005ebf  jz      short loc_180005EF0
0x180005ec1  sub     eax, 1
0x180005ec4  jz      short loc_180005EE7
0x180005ec6  sub     eax, 1
0x180005ec9  jz      short loc_180005EDE
0x180005ecb  cmp     eax, 1
0x180005ece  jz      short loc_180005ED5
0x180005ed0  mov     rax, rdx
0x180005ed3  jmp     short loc_180005E79
0x180005ed5  lea     rax, aSfStatusReqRea; "SF_STATUS_REQ_READ_NEXT"
0x180005edc  jmp     short loc_180005E79
0x180005ede  lea     rax, aSfStatusReqErr; "SF_STATUS_REQ_ERROR"
0x180005ee5  jmp     short loc_180005E79
0x180005ee7  lea     rax, aSfStatusReqHan; "SF_STATUS_REQ_HANDLED_NOTIFICATION"
0x180005eee  jmp     short loc_180005E79
0x180005ef0  lea     rax, aSfStatusReqNex; "SF_STATUS_REQ_NEXT_NOTIFICATION"
0x180005ef7  jmp     short loc_180005E79
0x180005ef9  lea     rax, aSfStatusReqFin; "SF_STATUS_REQ_FINISHED_KEEP_CONN"
0x180005f00  jmp     loc_180005E79
```
