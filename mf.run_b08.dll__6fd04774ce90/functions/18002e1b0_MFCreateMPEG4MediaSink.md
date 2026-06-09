# MFCreateMPEG4MediaSink

- ea: `0x18002e1b0`
- end: `0x18002e3a8`
- name: `MFCreateMPEG4MediaSink`
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
- `0x18002e1b0`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e205`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e205`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e2e7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e227`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e2e7`

## string_xrefs

- `0x18002e1d3`: `MFCreateMPEG4MediaSink_Stub`
- `0x18002e285`: `MFCreateMPEG4MediaSink_Stub`
- `0x18002e345`: `MFCreateMPEG4MediaSink_Stub`

## pseudocode

```c
HRESULT __stdcall MFCreateMPEG4MediaSink(
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
  sub_18000F370(v17, "MFCreateMPEG4MediaSink_Stub", 217);
  Instance = CoCreateInstance(&stru_18006F1F8, 0, 1u, &stru_1800701F8, ppv);
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
          sub_180034B38(v15, "MFCreateMPEG4MediaSink_Stub", 218, (unsigned int)Instance);
      }
      if ( byte_180084958 )
      {
        v12 = 13;
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
        sub_180034B38(v11, "MFCreateMPEG4MediaSink_Stub", 217, (unsigned int)Instance);
    }
    if ( byte_180084958 )
    {
      v12 = 12;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v12, &unk_180070010, 0, Instance);
    }
  }
  sub_1800104B0(v17);
  sub_180018064(ppv);
  return Instance;
}

```

## disassembly

```asm
0x18002e1b0  push    rbx
0x18002e1b2  push    rbp
0x18002e1b3  push    rsi
0x18002e1b4  push    rdi
0x18002e1b5  push    r14
0x18002e1b7  sub     rsp, 40h
0x18002e1bb  mov     rsi, r8
0x18002e1be  mov     [rsp+68h+var_30], 0
0x18002e1c7  mov     rbp, rdx
0x18002e1ca  mov     r14, rcx
0x18002e1cd  mov     r8d, 0D9h
0x18002e1d3  lea     rdx, aMfcreatempeg4m_0; "MFCreateMPEG4MediaSink_Stub"
0x18002e1da  lea     rcx, [rsp+68h+var_38]
0x18002e1df  mov     rdi, r9
0x18002e1e2  call    sub_18000F370
0x18002e1e7  xor     edx, edx; pUnkOuter
0x18002e1e9  lea     rax, [rsp+68h+var_30]
0x18002e1ee  lea     r9, stru_1800701F8; riid
0x18002e1f5  mov     [rsp+68h+ppv], rax; ppv
0x18002e1fa  lea     rcx, stru_18006F1F8; rclsid
0x18002e201  lea     r8d, [rdx+1]; dwClsContext
0x18002e205  call    cs:CoCreateInstance
0x18002e20c  nop     dword ptr [rax+rax+00h]
0x18002e211  mov     ebx, eax
0x18002e213  test    eax, eax
0x18002e215  jns     loc_18002E2B1
0x18002e21b  mov     rcx, cs:qword_180084A30
0x18002e222  test    rcx, rcx
0x18002e225  jnz     short loc_18002E26F
0x18002e227  call    cs:MFGetCallStackTracingWeakReference
0x18002e22e  nop     dword ptr [rax+rax+00h]
0x18002e233  mov     cs:qword_180084A30, rax
0x18002e23a  mov     rcx, rax
0x18002e23d  test    rax, rax
0x18002e240  jz      short loc_18002E261
0x18002e242  mov     rax, [rax]
0x18002e245  mov     edx, 7F0h
0x18002e24a  mov     rax, [rax+8]
0x18002e24e  call    cs:__guard_dispatch_icall_fptr
0x18002e254  test    eax, eax
0x18002e256  jz      short loc_18002E261
0x18002e258  mov     rcx, cs:qword_180084A30
0x18002e25f  jmp     short loc_18002E26F
0x18002e261  lea     rcx, qword_180083DB0
0x18002e268  mov     cs:qword_180084A30, rcx
0x18002e26f  cmp     byte ptr [rcx+8], 0
0x18002e273  jz      short loc_18002E29A
0x18002e275  call    sub_180010600
0x18002e27a  cmp     [rax+7CCh], ebx
0x18002e280  jz      short loc_18002E29A
0x18002e282  mov     r9d, ebx
0x18002e285  lea     rdx, aMfcreatempeg4m_0; "MFCreateMPEG4MediaSink_Stub"
0x18002e28c  mov     r8d, 0D9h
0x18002e292  mov     rcx, rax
0x18002e295  call    sub_180034B38
0x18002e29a  cmp     cs:byte_180084958, 1
0x18002e2a1  jb      loc_18002E386
0x18002e2a7  mov     edx, 0Ch
0x18002e2ac  jmp     loc_18002E368
0x18002e2b1  mov     rcx, [rsp+68h+var_30]
0x18002e2b6  mov     r9, rsi
0x18002e2b9  mov     r8, rbp
0x18002e2bc  mov     [rsp+68h+ppv], rdi
0x18002e2c1  mov     rdx, r14
0x18002e2c4  mov     rax, [rcx]
0x18002e2c7  mov     rax, [rax+18h]
0x18002e2cb  call    cs:__guard_dispatch_icall_fptr
0x18002e2d1  mov     ebx, eax
0x18002e2d3  test    eax, eax
0x18002e2d5  jns     loc_18002E386
0x18002e2db  mov     rcx, cs:qword_180084A30
0x18002e2e2  test    rcx, rcx
0x18002e2e5  jnz     short loc_18002E32F
0x18002e2e7  call    cs:MFGetCallStackTracingWeakReference
0x18002e2ee  nop     dword ptr [rax+rax+00h]
0x18002e2f3  mov     cs:qword_180084A30, rax
0x18002e2fa  mov     rcx, rax
0x18002e2fd  test    rax, rax
0x18002e300  jz      short loc_18002E321
0x18002e302  mov     rax, [rax]
0x18002e305  mov     edx, 7F0h
0x18002e30a  mov     rax, [rax+8]
0x18002e30e  call    cs:__guard_dispatch_icall_fptr
0x18002e314  test    eax, eax
0x18002e316  jz      short loc_18002E321
0x18002e318  mov     rcx, cs:qword_180084A30
0x18002e31f  jmp     short loc_18002E32F
0x18002e321  lea     rcx, qword_180083DB0
0x18002e328  mov     cs:qword_180084A30, rcx
0x18002e32f  cmp     byte ptr [rcx+8], 0
0x18002e333  jz      short loc_18002E35A
0x18002e335  call    sub_180010600
0x18002e33a  cmp     [rax+7CCh], ebx
0x18002e340  jz      short loc_18002E35A
0x18002e342  mov     r9d, ebx
0x18002e345  lea     rdx, aMfcreatempeg4m_0; "MFCreateMPEG4MediaSink_Stub"
0x18002e34c  mov     r8d, 0DAh
0x18002e352  mov     rcx, rax
0x18002e355  call    sub_180034B38
0x18002e35a  cmp     cs:byte_180084958, 1
0x18002e361  jb      short loc_18002E386
0x18002e363  mov     edx, 0Dh
0x18002e368  mov     rcx, cs:RequestContext
0x18002e36f  lea     r8, unk_180070010
0x18002e376  xor     r9d, r9d
0x18002e379  mov     dword ptr [rsp+68h+ppv], ebx
0x18002e37d  mov     rcx, [rcx+10h]
0x18002e381  call    sub_180018E70
0x18002e386  lea     rcx, [rsp+68h+var_38]
0x18002e38b  call    sub_1800104B0
0x18002e390  lea     rcx, [rsp+68h+var_30]
0x18002e395  call    sub_180018064
0x18002e39a  mov     eax, ebx
0x18002e39c  add     rsp, 40h
0x18002e3a0  pop     r14
0x18002e3a2  pop     rdi
0x18002e3a3  pop     rsi
0x18002e3a4  pop     rbp
0x18002e3a5  pop     rbx
0x18002e3a6  retn
```
