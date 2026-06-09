# MFCreateADTSMediaSink

- ea: `0x18002d870`
- end: `0x18002da64`
- name: `MFCreateADTSMediaSink`
- size: `500`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018064`
- `0x180018e70`
- `0x18002d870`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d8c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d8c0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d8e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d9a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d8e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002d9a2`

## string_xrefs

- `0x18002d892`: `MFCreateADTSMediaSink_Stub`
- `0x18002d940`: `MFCreateADTSMediaSink_Stub`
- `0x18002da00`: `MFCreateADTSMediaSink_Stub`

## pseudocode

```c
__int64 __fastcall MFCreateADTSMediaSink(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT Instance; // ebx
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  LPVOID ppv[7]; // [rsp+30h] [rbp-38h] BYREF
  char v16; // [rsp+88h] [rbp+20h] BYREF

  ppv[0] = 0;
  sub_18000F370(&v16, "MFCreateADTSMediaSink_Stub", 283);
  Instance = CoCreateInstance(&stru_18006F228, 0, 1u, &stru_1800701F8, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64, __int64))(*(_QWORD *)ppv[0] + 24LL))(
                 ppv[0],
                 a1,
                 0,
                 a2,
                 a3);
    if ( Instance < 0 )
    {
      v11 = (__int64 *)qword_180084A30;
      if ( !qword_180084A30 )
      {
        v12 = MFGetCallStackTracingWeakReference(0);
        qword_180084A30 = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)qword_180084A30;
        }
        else
        {
          v11 = &qword_180083DB0;
          qword_180084A30 = (__int64)&qword_180083DB0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = sub_180010600();
        if ( *(_DWORD *)(v13 + 1996) != Instance )
          sub_180034B38(v13, "MFCreateADTSMediaSink_Stub", 284, (unsigned int)Instance);
      }
      if ( byte_180084958 )
      {
        v10 = 21;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v7 = (__int64 *)qword_180084A30;
    if ( !qword_180084A30 )
    {
      v8 = MFGetCallStackTracingWeakReference(0);
      qword_180084A30 = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)qword_180084A30;
      }
      else
      {
        v7 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = sub_180010600();
      if ( *(_DWORD *)(v9 + 1996) != Instance )
        sub_180034B38(v9, "MFCreateADTSMediaSink_Stub", 283, (unsigned int)Instance);
    }
    if ( byte_180084958 )
    {
      v10 = 20;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v10, qword_180070010, 0, Instance);
    }
  }
  sub_1800104B0(&v16);
  sub_180018064(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002d870  mov     rax, rsp
0x18002d873  push    rbx
0x18002d874  push    rbp
0x18002d875  push    rsi
0x18002d876  push    rdi
0x18002d877  sub     rsp, 48h
0x18002d87b  mov     rdi, r8
0x18002d87e  mov     qword ptr [rax-38h], 0
0x18002d886  mov     rsi, rdx
0x18002d889  mov     rbp, rcx
0x18002d88c  mov     r8d, 11Bh
0x18002d892  lea     rdx, aMfcreateadtsme_0; "MFCreateADTSMediaSink_Stub"
0x18002d899  lea     rcx, [rax+20h]
0x18002d89d  call    sub_18000F370
0x18002d8a2  xor     edx, edx; pUnkOuter
0x18002d8a4  lea     rax, [rsp+68h+var_38]
0x18002d8a9  lea     r9, stru_1800701F8; riid
0x18002d8b0  mov     [rsp+68h+ppv], rax; ppv
0x18002d8b5  lea     rcx, stru_18006F228; rclsid
0x18002d8bc  lea     r8d, [rdx+1]; dwClsContext
0x18002d8c0  call    cs:CoCreateInstance
0x18002d8c7  nop     dword ptr [rax+rax+00h]
0x18002d8cc  mov     ebx, eax
0x18002d8ce  test    eax, eax
0x18002d8d0  jns     loc_18002D96C
0x18002d8d6  mov     rcx, cs:qword_180084A30
0x18002d8dd  test    rcx, rcx
0x18002d8e0  jnz     short loc_18002D92A
0x18002d8e2  call    cs:MFGetCallStackTracingWeakReference
0x18002d8e9  nop     dword ptr [rax+rax+00h]
0x18002d8ee  mov     cs:qword_180084A30, rax
0x18002d8f5  mov     rcx, rax
0x18002d8f8  test    rax, rax
0x18002d8fb  jz      short loc_18002D91C
0x18002d8fd  mov     rax, [rax]
0x18002d900  mov     edx, 7F0h
0x18002d905  mov     rax, [rax+8]
0x18002d909  call    cs:__guard_dispatch_icall_fptr
0x18002d90f  test    eax, eax
0x18002d911  jz      short loc_18002D91C
0x18002d913  mov     rcx, cs:qword_180084A30
0x18002d91a  jmp     short loc_18002D92A
0x18002d91c  lea     rcx, qword_180083DB0
0x18002d923  mov     cs:qword_180084A30, rcx
0x18002d92a  cmp     byte ptr [rcx+8], 0
0x18002d92e  jz      short loc_18002D955
0x18002d930  call    sub_180010600
0x18002d935  cmp     [rax+7CCh], ebx
0x18002d93b  jz      short loc_18002D955
0x18002d93d  mov     r9d, ebx
0x18002d940  lea     rdx, aMfcreateadtsme_0; "MFCreateADTSMediaSink_Stub"
0x18002d947  mov     r8d, 11Bh
0x18002d94d  mov     rcx, rax
0x18002d950  call    sub_180034B38
0x18002d955  cmp     cs:byte_180084958, 1
0x18002d95c  jb      loc_18002DA41
0x18002d962  mov     edx, 14h
0x18002d967  jmp     loc_18002DA23
0x18002d96c  mov     rcx, [rsp+68h+var_38]
0x18002d971  mov     r9, rsi
0x18002d974  xor     r8d, r8d
0x18002d977  mov     [rsp+68h+ppv], rdi
0x18002d97c  mov     rdx, rbp
0x18002d97f  mov     rax, [rcx]
0x18002d982  mov     rax, [rax+18h]
0x18002d986  call    cs:__guard_dispatch_icall_fptr
0x18002d98c  mov     ebx, eax
0x18002d98e  test    eax, eax
0x18002d990  jns     loc_18002DA41
0x18002d996  mov     rcx, cs:qword_180084A30
0x18002d99d  test    rcx, rcx
0x18002d9a0  jnz     short loc_18002D9EA
0x18002d9a2  call    cs:MFGetCallStackTracingWeakReference
0x18002d9a9  nop     dword ptr [rax+rax+00h]
0x18002d9ae  mov     cs:qword_180084A30, rax
0x18002d9b5  mov     rcx, rax
0x18002d9b8  test    rax, rax
0x18002d9bb  jz      short loc_18002D9DC
0x18002d9bd  mov     rax, [rax]
0x18002d9c0  mov     edx, 7F0h
0x18002d9c5  mov     rax, [rax+8]
0x18002d9c9  call    cs:__guard_dispatch_icall_fptr
0x18002d9cf  test    eax, eax
0x18002d9d1  jz      short loc_18002D9DC
0x18002d9d3  mov     rcx, cs:qword_180084A30
0x18002d9da  jmp     short loc_18002D9EA
0x18002d9dc  lea     rcx, qword_180083DB0
0x18002d9e3  mov     cs:qword_180084A30, rcx
0x18002d9ea  cmp     byte ptr [rcx+8], 0
0x18002d9ee  jz      short loc_18002DA15
0x18002d9f0  call    sub_180010600
0x18002d9f5  cmp     [rax+7CCh], ebx
0x18002d9fb  jz      short loc_18002DA15
0x18002d9fd  mov     r9d, ebx
0x18002da00  lea     rdx, aMfcreateadtsme_0; "MFCreateADTSMediaSink_Stub"
0x18002da07  mov     r8d, 11Ch
0x18002da0d  mov     rcx, rax
0x18002da10  call    sub_180034B38
0x18002da15  cmp     cs:byte_180084958, 1
0x18002da1c  jb      short loc_18002DA41
0x18002da1e  mov     edx, 15h
0x18002da23  mov     rcx, cs:RequestContext
0x18002da2a  lea     r8, qword_180070010
0x18002da31  xor     r9d, r9d
0x18002da34  mov     dword ptr [rsp+68h+ppv], ebx
0x18002da38  mov     rcx, [rcx+10h]
0x18002da3c  call    sub_180018E70
0x18002da41  lea     rcx, [rsp+68h+arg_18]
0x18002da49  call    sub_1800104B0
0x18002da4e  lea     rcx, [rsp+68h+var_38]
0x18002da53  call    sub_180018064
0x18002da58  mov     eax, ebx
0x18002da5a  add     rsp, 48h
0x18002da5e  pop     rdi
0x18002da5f  pop     rsi
0x18002da60  pop     rbp
0x18002da61  pop     rbx
0x18002da62  retn
```
