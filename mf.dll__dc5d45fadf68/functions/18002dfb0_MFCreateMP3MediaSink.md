# MFCreateMP3MediaSink

- ea: `0x18002dfb0`
- end: `0x18002e1aa`
- name: `MFCreateMP3MediaSink`
- size: `506`
- prototype: `HRESULT __stdcall(IMFByteStream *pTargetByteStream, IMFMediaSink **ppMediaSink)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018064`
- `0x180018e70`
- `0x18002dfb0`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e002`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e002`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e024`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e0e4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e024`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e0e4`

## string_xrefs

- `0x18002dfce`: `MFCreateMP3MediaSink_Stub`
- `0x18002e082`: `MFCreateMP3MediaSink_Stub`
- `0x18002e142`: `MFCreateMP3MediaSink_Stub`

## pseudocode

```c
HRESULT __stdcall MFCreateMP3MediaSink(IMFByteStream *pTargetByteStream, IMFMediaSink **ppMediaSink)
{
  int v4; // ebx
  __int64 *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  char v13; // [rsp+50h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+20h] BYREF

  ppv = 0;
  sub_18000F370(&v13, "MFCreateMP3MediaSink_Stub", 200);
  v4 = CoCreateInstance(&stru_18006F1D8, 0, 1u, &stru_1800701F8, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, IMFByteStream *, _QWORD, _QWORD, IMFMediaSink **))(*(_QWORD *)ppv + 24LL))(
           ppv,
           pTargetByteStream,
           0,
           0,
           ppMediaSink);
    if ( v4 < 0 )
    {
      v9 = (__int64 *)qword_180084A30;
      if ( !qword_180084A30 )
      {
        v10 = MFGetCallStackTracingWeakReference();
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
        if ( *(_DWORD *)(v11 + 1996) != v4 )
          sub_180034B38(v11, "MFCreateMP3MediaSink_Stub", 201, (unsigned int)v4);
      }
      if ( byte_180084958 )
      {
        v8 = 11;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v5 = (__int64 *)qword_180084A30;
    if ( !qword_180084A30 )
    {
      v6 = MFGetCallStackTracingWeakReference();
      qword_180084A30 = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)qword_180084A30;
      }
      else
      {
        v5 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = sub_180010600();
      if ( *(_DWORD *)(v7 + 1996) != v4 )
        sub_180034B38(v7, "MFCreateMP3MediaSink_Stub", 200, (unsigned int)v4);
    }
    if ( byte_180084958 )
    {
      v8 = 10;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v8, qword_180070010, 0, v4);
    }
  }
  sub_1800104B0(&v13);
  sub_180018064(&ppv);
  return v4;
}

```

## disassembly

```asm
0x18002dfb0  mov     rax, rsp
0x18002dfb3  mov     [rax+8], rbx
0x18002dfb7  mov     [rax+10h], rsi
0x18002dfbb  push    rdi
0x18002dfbc  sub     rsp, 30h
0x18002dfc0  mov     rdi, rdx
0x18002dfc3  mov     qword ptr [rax+20h], 0
0x18002dfcb  mov     rsi, rcx
0x18002dfce  lea     rdx, aMfcreatemp3med_0; "MFCreateMP3MediaSink_Stub"
0x18002dfd5  lea     rcx, [rax+18h]
0x18002dfd9  mov     r8d, 0C8h
0x18002dfdf  call    sub_18000F370
0x18002dfe4  xor     edx, edx; pUnkOuter
0x18002dfe6  lea     rax, [rsp+38h+arg_18]
0x18002dfeb  lea     r9, stru_1800701F8; riid
0x18002dff2  mov     [rsp+38h+ppv], rax; ppv
0x18002dff7  lea     rcx, stru_18006F1D8; rclsid
0x18002dffe  lea     r8d, [rdx+1]; dwClsContext
0x18002e002  call    cs:CoCreateInstance
0x18002e009  nop     dword ptr [rax+rax+00h]
0x18002e00e  mov     ebx, eax
0x18002e010  test    eax, eax
0x18002e012  jns     loc_18002E0AE
0x18002e018  mov     rcx, cs:qword_180084A30
0x18002e01f  test    rcx, rcx
0x18002e022  jnz     short loc_18002E06C
0x18002e024  call    cs:MFGetCallStackTracingWeakReference
0x18002e02b  nop     dword ptr [rax+rax+00h]
0x18002e030  mov     cs:qword_180084A30, rax
0x18002e037  mov     rcx, rax
0x18002e03a  test    rax, rax
0x18002e03d  jz      short loc_18002E05E
0x18002e03f  mov     rax, [rax]
0x18002e042  mov     edx, 7F0h
0x18002e047  mov     rax, [rax+8]
0x18002e04b  call    cs:__guard_dispatch_icall_fptr
0x18002e051  test    eax, eax
0x18002e053  jz      short loc_18002E05E
0x18002e055  mov     rcx, cs:qword_180084A30
0x18002e05c  jmp     short loc_18002E06C
0x18002e05e  lea     rcx, qword_180083DB0
0x18002e065  mov     cs:qword_180084A30, rcx
0x18002e06c  cmp     byte ptr [rcx+8], 0
0x18002e070  jz      short loc_18002E097
0x18002e072  call    sub_180010600
0x18002e077  cmp     [rax+7CCh], ebx
0x18002e07d  jz      short loc_18002E097
0x18002e07f  mov     r9d, ebx
0x18002e082  lea     rdx, aMfcreatemp3med_0; "MFCreateMP3MediaSink_Stub"
0x18002e089  mov     r8d, 0C8h
0x18002e08f  mov     rcx, rax
0x18002e092  call    sub_180034B38
0x18002e097  cmp     cs:byte_180084958, 1
0x18002e09e  jb      loc_18002E183
0x18002e0a4  mov     edx, 0Ah
0x18002e0a9  jmp     loc_18002E165
0x18002e0ae  mov     rcx, [rsp+38h+arg_18]
0x18002e0b3  xor     r9d, r9d
0x18002e0b6  xor     r8d, r8d
0x18002e0b9  mov     [rsp+38h+ppv], rdi
0x18002e0be  mov     rdx, rsi
0x18002e0c1  mov     rax, [rcx]
0x18002e0c4  mov     rax, [rax+18h]
0x18002e0c8  call    cs:__guard_dispatch_icall_fptr
0x18002e0ce  mov     ebx, eax
0x18002e0d0  test    eax, eax
0x18002e0d2  jns     loc_18002E183
0x18002e0d8  mov     rcx, cs:qword_180084A30
0x18002e0df  test    rcx, rcx
0x18002e0e2  jnz     short loc_18002E12C
0x18002e0e4  call    cs:MFGetCallStackTracingWeakReference
0x18002e0eb  nop     dword ptr [rax+rax+00h]
0x18002e0f0  mov     cs:qword_180084A30, rax
0x18002e0f7  mov     rcx, rax
0x18002e0fa  test    rax, rax
0x18002e0fd  jz      short loc_18002E11E
0x18002e0ff  mov     rax, [rax]
0x18002e102  mov     edx, 7F0h
0x18002e107  mov     rax, [rax+8]
0x18002e10b  call    cs:__guard_dispatch_icall_fptr
0x18002e111  test    eax, eax
0x18002e113  jz      short loc_18002E11E
0x18002e115  mov     rcx, cs:qword_180084A30
0x18002e11c  jmp     short loc_18002E12C
0x18002e11e  lea     rcx, qword_180083DB0
0x18002e125  mov     cs:qword_180084A30, rcx
0x18002e12c  cmp     byte ptr [rcx+8], 0
0x18002e130  jz      short loc_18002E157
0x18002e132  call    sub_180010600
0x18002e137  cmp     [rax+7CCh], ebx
0x18002e13d  jz      short loc_18002E157
0x18002e13f  mov     r9d, ebx
0x18002e142  lea     rdx, aMfcreatemp3med_0; "MFCreateMP3MediaSink_Stub"
0x18002e149  mov     r8d, 0C9h
0x18002e14f  mov     rcx, rax
0x18002e152  call    sub_180034B38
0x18002e157  cmp     cs:byte_180084958, 1
0x18002e15e  jb      short loc_18002E183
0x18002e160  mov     edx, 0Bh
0x18002e165  mov     rcx, cs:RequestContext
0x18002e16c  lea     r8, qword_180070010
0x18002e173  xor     r9d, r9d
0x18002e176  mov     dword ptr [rsp+38h+ppv], ebx
0x18002e17a  mov     rcx, [rcx+10h]
0x18002e17e  call    sub_180018E70
0x18002e183  lea     rcx, [rsp+38h+arg_10]
0x18002e188  call    sub_1800104B0
0x18002e18d  lea     rcx, [rsp+38h+arg_18]
0x18002e192  call    sub_180018064
0x18002e197  mov     rsi, [rsp+38h+arg_8]
0x18002e19c  mov     eax, ebx
0x18002e19e  mov     rbx, [rsp+38h+arg_0]
0x18002e1a3  add     rsp, 30h
0x18002e1a7  pop     rdi
0x18002e1a8  retn
```
