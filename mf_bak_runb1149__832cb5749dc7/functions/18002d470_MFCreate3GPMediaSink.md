# MFCreate3GPMediaSink

- ea: `0x18002d470`
- end: `0x18002d668`
- name: `MFCreate3GPMediaSink`
- size: `504`
- prototype: `HRESULT __stdcall(IMFByteStream *pIByteStream, IMFMediaType *pVideoMediaType, IMFMediaType *pAudioMediaType, IMFMediaSink **ppIMediaSink)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018064`
- `0x180018e70`
- `0x18002d470`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d4c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d4c5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d4e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d5a7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d4e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d5a7`

## string_xrefs

- `0x18002d493`: `MFCreate3GPMediaSink_Stub`
- `0x18002d545`: `MFCreate3GPMediaSink_Stub`
- `0x18002d605`: `MFCreate3GPMediaSink_Stub`

## pseudocode

```c
HRESULT __stdcall MFCreate3GPMediaSink(
        IMFByteStream *pIByteStream,
        IMFMediaType *pVideoMediaType,
        IMFMediaType *pAudioMediaType,
        IMFMediaSink **ppIMediaSink)
{
  int Instance; // ebx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  _BYTE v17[8]; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv[6]; // [rsp+38h] [rbp-30h] BYREF

  ppv[0] = 0;
  sub_18000F370(v17, "MFCreate3GPMediaSink_Stub", 251);
  Instance = CoCreateInstance(&stru_18006F1E8, 0, 1u, &stru_1800701F8, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, IMFByteStream *, IMFMediaType *, IMFMediaType *, IMFMediaSink **))(*(_QWORD *)ppv[0] + 24LL))(
                 ppv[0],
                 pIByteStream,
                 pVideoMediaType,
                 pAudioMediaType,
                 ppIMediaSink);
    if ( Instance < 0 )
    {
      v13 = (__int64 *)qword_180084A30;
      if ( !qword_180084A30 )
      {
        v14 = MFGetCallStackTracingWeakReference(0);
        qword_180084A30 = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)qword_180084A30;
        }
        else
        {
          v13 = &qword_180083DB0;
          qword_180084A30 = (__int64)&qword_180083DB0;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = sub_180010600();
        if ( *(_DWORD *)(v15 + 1996) != Instance )
          sub_180034B38(v15, "MFCreate3GPMediaSink_Stub", 252, (unsigned int)Instance);
      }
      if ( byte_180084958 )
      {
        v12 = 17;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v9 = (__int64 *)qword_180084A30;
    if ( !qword_180084A30 )
    {
      v10 = MFGetCallStackTracingWeakReference(0);
      qword_180084A30 = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)qword_180084A30;
      }
      else
      {
        v9 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = sub_180010600();
      if ( *(_DWORD *)(v11 + 1996) != Instance )
        sub_180034B38(v11, "MFCreate3GPMediaSink_Stub", 251, (unsigned int)Instance);
    }
    if ( byte_180084958 )
    {
      v12 = 16;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v12, qword_180070010, 0, Instance);
    }
  }
  sub_1800104B0(v17);
  sub_180018064(ppv);
  return Instance;
}

```

## disassembly

```asm
0x18002d470  push    rbx
0x18002d472  push    rbp
0x18002d473  push    rsi
0x18002d474  push    rdi
0x18002d475  push    r14
0x18002d477  sub     rsp, 40h
0x18002d47b  mov     rsi, r8
0x18002d47e  mov     [rsp+68h+var_30], 0
0x18002d487  mov     rbp, rdx
0x18002d48a  mov     r14, rcx
0x18002d48d  mov     r8d, 0FBh
0x18002d493  lea     rdx, aMfcreate3gpmed_0; "MFCreate3GPMediaSink_Stub"
0x18002d49a  lea     rcx, [rsp+68h+var_38]
0x18002d49f  mov     rdi, r9
0x18002d4a2  call    sub_18000F370
0x18002d4a7  xor     edx, edx; pUnkOuter
0x18002d4a9  lea     rax, [rsp+68h+var_30]
0x18002d4ae  lea     r9, stru_1800701F8; riid
0x18002d4b5  mov     [rsp+68h+ppv], rax; ppv
0x18002d4ba  lea     rcx, stru_18006F1E8; rclsid
0x18002d4c1  lea     r8d, [rdx+1]; dwClsContext
0x18002d4c5  call    cs:CoCreateInstance
0x18002d4cc  nop     dword ptr [rax+rax+00h]
0x18002d4d1  mov     ebx, eax
0x18002d4d3  test    eax, eax
0x18002d4d5  jns     loc_18002D571
0x18002d4db  mov     rcx, cs:qword_180084A30
0x18002d4e2  test    rcx, rcx
0x18002d4e5  jnz     short loc_18002D52F
0x18002d4e7  call    cs:MFGetCallStackTracingWeakReference
0x18002d4ee  nop     dword ptr [rax+rax+00h]
0x18002d4f3  mov     cs:qword_180084A30, rax
0x18002d4fa  mov     rcx, rax
0x18002d4fd  test    rax, rax
0x18002d500  jz      short loc_18002D521
0x18002d502  mov     rax, [rax]
0x18002d505  mov     edx, 7F0h
0x18002d50a  mov     rax, [rax+8]
0x18002d50e  call    cs:__guard_dispatch_icall_fptr
0x18002d514  test    eax, eax
0x18002d516  jz      short loc_18002D521
0x18002d518  mov     rcx, cs:qword_180084A30
0x18002d51f  jmp     short loc_18002D52F
0x18002d521  lea     rcx, qword_180083DB0
0x18002d528  mov     cs:qword_180084A30, rcx
0x18002d52f  cmp     byte ptr [rcx+8], 0
0x18002d533  jz      short loc_18002D55A
0x18002d535  call    sub_180010600
0x18002d53a  cmp     [rax+7CCh], ebx
0x18002d540  jz      short loc_18002D55A
0x18002d542  mov     r9d, ebx
0x18002d545  lea     rdx, aMfcreate3gpmed_0; "MFCreate3GPMediaSink_Stub"
0x18002d54c  mov     r8d, 0FBh
0x18002d552  mov     rcx, rax
0x18002d555  call    sub_180034B38
0x18002d55a  cmp     cs:byte_180084958, 1
0x18002d561  jb      loc_18002D646
0x18002d567  mov     edx, 10h
0x18002d56c  jmp     loc_18002D628
0x18002d571  mov     rcx, [rsp+68h+var_30]
0x18002d576  mov     r9, rsi
0x18002d579  mov     r8, rbp
0x18002d57c  mov     [rsp+68h+ppv], rdi
0x18002d581  mov     rdx, r14
0x18002d584  mov     rax, [rcx]
0x18002d587  mov     rax, [rax+18h]
0x18002d58b  call    cs:__guard_dispatch_icall_fptr
0x18002d591  mov     ebx, eax
0x18002d593  test    eax, eax
0x18002d595  jns     loc_18002D646
0x18002d59b  mov     rcx, cs:qword_180084A30
0x18002d5a2  test    rcx, rcx
0x18002d5a5  jnz     short loc_18002D5EF
0x18002d5a7  call    cs:MFGetCallStackTracingWeakReference
0x18002d5ae  nop     dword ptr [rax+rax+00h]
0x18002d5b3  mov     cs:qword_180084A30, rax
0x18002d5ba  mov     rcx, rax
0x18002d5bd  test    rax, rax
0x18002d5c0  jz      short loc_18002D5E1
0x18002d5c2  mov     rax, [rax]
0x18002d5c5  mov     edx, 7F0h
0x18002d5ca  mov     rax, [rax+8]
0x18002d5ce  call    cs:__guard_dispatch_icall_fptr
0x18002d5d4  test    eax, eax
0x18002d5d6  jz      short loc_18002D5E1
0x18002d5d8  mov     rcx, cs:qword_180084A30
0x18002d5df  jmp     short loc_18002D5EF
0x18002d5e1  lea     rcx, qword_180083DB0
0x18002d5e8  mov     cs:qword_180084A30, rcx
0x18002d5ef  cmp     byte ptr [rcx+8], 0
0x18002d5f3  jz      short loc_18002D61A
0x18002d5f5  call    sub_180010600
0x18002d5fa  cmp     [rax+7CCh], ebx
0x18002d600  jz      short loc_18002D61A
0x18002d602  mov     r9d, ebx
0x18002d605  lea     rdx, aMfcreate3gpmed_0; "MFCreate3GPMediaSink_Stub"
0x18002d60c  mov     r8d, 0FCh
0x18002d612  mov     rcx, rax
0x18002d615  call    sub_180034B38
0x18002d61a  cmp     cs:byte_180084958, 1
0x18002d621  jb      short loc_18002D646
0x18002d623  mov     edx, 11h
0x18002d628  mov     rcx, cs:RequestContext
0x18002d62f  lea     r8, qword_180070010
0x18002d636  xor     r9d, r9d
0x18002d639  mov     dword ptr [rsp+68h+ppv], ebx
0x18002d63d  mov     rcx, [rcx+10h]
0x18002d641  call    sub_180018E70
0x18002d646  lea     rcx, [rsp+68h+var_38]
0x18002d64b  call    sub_1800104B0
0x18002d650  lea     rcx, [rsp+68h+var_30]
0x18002d655  call    sub_180018064
0x18002d65a  mov     eax, ebx
0x18002d65c  add     rsp, 40h
0x18002d660  pop     r14
0x18002d662  pop     rdi
0x18002d663  pop     rsi
0x18002d664  pop     rbp
0x18002d665  pop     rbx
0x18002d666  retn
```
