# MFCreateMuxSink

- ea: `0x18002e3b0`
- end: `0x18002e5b4`
- name: `MFCreateMuxSink`
- size: `516`
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
- `0x18002e3b0`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e405`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e405`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e4f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e427`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002e4f3`

## string_xrefs

- `0x18002e3d3`: `MFCreateMuxSink_Stub`
- `0x18002e485`: `MFCreateMuxSink_Stub`
- `0x18002e551`: `MFCreateMuxSink_Stub`

## pseudocode

```c
__int64 __fastcall MFCreateMuxSink(_OWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  HRESULT v8; // ebx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-40h] BYREF
  _OWORD v20[3]; // [rsp+40h] [rbp-38h] BYREF

  ppv = 0;
  sub_18000F370(v18, "MFCreateMuxSink_Stub", 315);
  v8 = CoCreateInstance(&stru_18006F238, 0, 1u, &stru_1800700A0, &ppv);
  if ( v8 >= 0 )
  {
    v13 = *(_QWORD *)ppv;
    v20[0] = *a1;
    v8 = (*(__int64 (__fastcall **)(LPVOID, _OWORD *, __int64, __int64, __int64))(v13 + 24))(ppv, v20, a2, a3, a4);
    if ( v8 < 0 )
    {
      v14 = (__int64 *)qword_180084A30;
      if ( !qword_180084A30 )
      {
        v15 = MFGetCallStackTracingWeakReference(0);
        qword_180084A30 = v15;
        if ( v15 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
        {
          v14 = (__int64 *)qword_180084A30;
        }
        else
        {
          v14 = &qword_180083DB0;
          qword_180084A30 = (__int64)&qword_180083DB0;
        }
      }
      if ( *((_BYTE *)v14 + 8) )
      {
        v16 = sub_180010600();
        if ( *(_DWORD *)(v16 + 1996) != v8 )
          sub_180034B38(v16, "MFCreateMuxSink_Stub", 316, (unsigned int)v8);
      }
      if ( byte_180084958 )
      {
        v12 = 23;
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
      if ( *(_DWORD *)(v11 + 1996) != v8 )
        sub_180034B38(v11, "MFCreateMuxSink_Stub", 315, (unsigned int)v8);
    }
    if ( byte_180084958 )
    {
      v12 = 22;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v12, &unk_180070010, 0, v8);
    }
  }
  sub_1800104B0(v18);
  sub_180018064(&ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002e3b0  push    rbx
0x18002e3b2  push    rbp
0x18002e3b3  push    rsi
0x18002e3b4  push    rdi
0x18002e3b5  push    r14
0x18002e3b7  sub     rsp, 50h
0x18002e3bb  mov     rsi, r8
0x18002e3be  mov     [rsp+78h+var_40], 0
0x18002e3c7  mov     rbp, rdx
0x18002e3ca  mov     r14, rcx
0x18002e3cd  mov     r8d, 13Bh
0x18002e3d3  lea     rdx, aMfcreatemuxsin_0; "MFCreateMuxSink_Stub"
0x18002e3da  lea     rcx, [rsp+78h+var_48]
0x18002e3df  mov     rdi, r9
0x18002e3e2  call    sub_18000F370
0x18002e3e7  xor     edx, edx; pUnkOuter
0x18002e3e9  lea     rax, [rsp+78h+var_40]
0x18002e3ee  lea     r9, stru_1800700A0; riid
0x18002e3f5  mov     [rsp+78h+ppv], rax; ppv
0x18002e3fa  lea     rcx, stru_18006F238; rclsid
0x18002e401  lea     r8d, [rdx+1]; dwClsContext
0x18002e405  call    cs:CoCreateInstance
0x18002e40c  nop     dword ptr [rax+rax+00h]
0x18002e411  mov     ebx, eax
0x18002e413  test    eax, eax
0x18002e415  jns     loc_18002E4B1
0x18002e41b  mov     rcx, cs:qword_180084A30
0x18002e422  test    rcx, rcx
0x18002e425  jnz     short loc_18002E46F
0x18002e427  call    cs:MFGetCallStackTracingWeakReference
0x18002e42e  nop     dword ptr [rax+rax+00h]
0x18002e433  mov     cs:qword_180084A30, rax
0x18002e43a  mov     rcx, rax
0x18002e43d  test    rax, rax
0x18002e440  jz      short loc_18002E461
0x18002e442  mov     rax, [rax]
0x18002e445  mov     edx, 7F0h
0x18002e44a  mov     rax, [rax+8]
0x18002e44e  call    cs:__guard_dispatch_icall_fptr
0x18002e454  test    eax, eax
0x18002e456  jz      short loc_18002E461
0x18002e458  mov     rcx, cs:qword_180084A30
0x18002e45f  jmp     short loc_18002E46F
0x18002e461  lea     rcx, qword_180083DB0
0x18002e468  mov     cs:qword_180084A30, rcx
0x18002e46f  cmp     byte ptr [rcx+8], 0
0x18002e473  jz      short loc_18002E49A
0x18002e475  call    sub_180010600
0x18002e47a  cmp     [rax+7CCh], ebx
0x18002e480  jz      short loc_18002E49A
0x18002e482  mov     r9d, ebx
0x18002e485  lea     rdx, aMfcreatemuxsin_0; "MFCreateMuxSink_Stub"
0x18002e48c  mov     r8d, 13Bh
0x18002e492  mov     rcx, rax
0x18002e495  call    sub_180034B38
0x18002e49a  cmp     cs:byte_180084958, 1
0x18002e4a1  jb      loc_18002E592
0x18002e4a7  mov     edx, 16h
0x18002e4ac  jmp     loc_18002E574
0x18002e4b1  mov     rcx, [rsp+78h+var_40]
0x18002e4b6  lea     rdx, [rsp+78h+var_38]
0x18002e4bb  movups  xmm0, xmmword ptr [r14]
0x18002e4bf  mov     r9, rsi
0x18002e4c2  mov     [rsp+78h+ppv], rdi
0x18002e4c7  mov     r8, rbp
0x18002e4ca  mov     rax, [rcx]
0x18002e4cd  movdqu  [rsp+78h+var_38], xmm0
0x18002e4d3  mov     rax, [rax+18h]
0x18002e4d7  call    cs:__guard_dispatch_icall_fptr
0x18002e4dd  mov     ebx, eax
0x18002e4df  test    eax, eax
0x18002e4e1  jns     loc_18002E592
0x18002e4e7  mov     rcx, cs:qword_180084A30
0x18002e4ee  test    rcx, rcx
0x18002e4f1  jnz     short loc_18002E53B
0x18002e4f3  call    cs:MFGetCallStackTracingWeakReference
0x18002e4fa  nop     dword ptr [rax+rax+00h]
0x18002e4ff  mov     cs:qword_180084A30, rax
0x18002e506  mov     rcx, rax
0x18002e509  test    rax, rax
0x18002e50c  jz      short loc_18002E52D
0x18002e50e  mov     rax, [rax]
0x18002e511  mov     edx, 7F0h
0x18002e516  mov     rax, [rax+8]
0x18002e51a  call    cs:__guard_dispatch_icall_fptr
0x18002e520  test    eax, eax
0x18002e522  jz      short loc_18002E52D
0x18002e524  mov     rcx, cs:qword_180084A30
0x18002e52b  jmp     short loc_18002E53B
0x18002e52d  lea     rcx, qword_180083DB0
0x18002e534  mov     cs:qword_180084A30, rcx
0x18002e53b  cmp     byte ptr [rcx+8], 0
0x18002e53f  jz      short loc_18002E566
0x18002e541  call    sub_180010600
0x18002e546  cmp     [rax+7CCh], ebx
0x18002e54c  jz      short loc_18002E566
0x18002e54e  mov     r9d, ebx
0x18002e551  lea     rdx, aMfcreatemuxsin_0; "MFCreateMuxSink_Stub"
0x18002e558  mov     r8d, 13Ch
0x18002e55e  mov     rcx, rax
0x18002e561  call    sub_180034B38
0x18002e566  cmp     cs:byte_180084958, 1
0x18002e56d  jb      short loc_18002E592
0x18002e56f  mov     edx, 17h
0x18002e574  mov     rcx, cs:RequestContext
0x18002e57b  lea     r8, unk_180070010
0x18002e582  xor     r9d, r9d
0x18002e585  mov     dword ptr [rsp+78h+ppv], ebx
0x18002e589  mov     rcx, [rcx+10h]
0x18002e58d  call    sub_180018E70
0x18002e592  lea     rcx, [rsp+78h+var_48]
0x18002e597  call    sub_1800104B0
0x18002e59c  lea     rcx, [rsp+78h+var_40]
0x18002e5a1  call    sub_180018064
0x18002e5a6  mov     eax, ebx
0x18002e5a8  add     rsp, 50h
0x18002e5ac  pop     r14
0x18002e5ae  pop     rdi
0x18002e5af  pop     rsi
0x18002e5b0  pop     rbp
0x18002e5b1  pop     rbx
0x18002e5b2  retn
```
