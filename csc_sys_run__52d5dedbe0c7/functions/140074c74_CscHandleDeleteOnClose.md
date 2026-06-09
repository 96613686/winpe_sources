# CscHandleDeleteOnClose

- ea: `0x140074c74`
- end: `0x140074fec`
- name: `CscHandleDeleteOnClose`
- size: `888`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x140074330`

## callees

- `0x1400017c0`
- `0x14000e100`
- `0x14000f8b0`
- `0x1400169d4`
- `0x140016a04`
- `0x140018930`
- `0x140019140`
- `0x14002f010`
- `0x14002f440`
- `0x14004fca4`
- `0x140074c74`
- `0x140086d64`
- `0x140088580`

## import_xrefs

- `rdbss!RxReleaseFcbPagingInMRx` at `0x140074fdb`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140074fdb`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x140074dce`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x140074dce`

## pseudocode

```c
__int64 __fastcall CscHandleDeleteOnClose(_QWORD *a1, char a2)
{
  char v4; // bl
  __int64 v5; // rsi
  __int64 v6; // r13
  char v7; // r14
  __int64 v8; // rdi
  __int64 result; // rax
  __int64 v10; // r8
  char v11; // bl
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // [rsp+20h] [rbp-99h]
  char v19; // [rsp+40h] [rbp-79h] BYREF
  char v20; // [rsp+41h] [rbp-78h] BYREF
  char v21[6]; // [rsp+42h] [rbp-77h] BYREF
  __int64 v22; // [rsp+48h] [rbp-71h] BYREF
  __int128 v23; // [rsp+50h] [rbp-69h] BYREF
  _WORD v24[40]; // [rsp+80h] [rbp-39h] BYREF

  v4 = 1;
  v23 = 0;
  memset(v24, 0, sizeof(v24));
  v5 = a1[7];
  v6 = a1[9];
  v7 = 0;
  v19 = 0;
  v20 = 0;
  CscGetContexts(a1, &v23);
  v8 = *((_QWORD *)&v23 + 1);
  result = CscStoreQueryInformationEntryEx(
             *(_QWORD *)(*((_QWORD *)&v23 + 1) + 56LL),
             0,
             (__int64)v24,
             0,
             &v19,
             (__int64)&v20,
             0);
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      result = WPP_SF_d(
                 WPP_GLOBAL_Control->AttachedDevice,
                 193,
                 WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                 (unsigned int)result);
    v4 = 0;
  }
  if ( !*(_DWORD *)(v8 + 32) )
  {
    if ( v19 || (result = *(unsigned int *)(v5 + 156), (result & 1) != 0) )
    {
      CscNotifyReportChange(a1, (unsigned int)(*(_WORD *)v5 == 0xEC21) + 1, 2);
      if ( !v19 )
      {
        if ( !a2 || v4 && (v24[0] & 0x400) != 0 )
        {
          v11 = 1;
          goto LABEL_16;
        }
        v7 = 1;
      }
      v11 = 0;
LABEL_16:
      LOBYTE(v10) = 1;
      RxAcquireExclusiveFcbPagingInMRx(a1, v5, v10);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        LOBYTE(v18) = v7 != 0 ? 89 : 78;
        LOBYTE(v14) = v11 != 0 ? 89 : 78;
        WPP_SF_cc(WPP_GLOBAL_Control->AttachedDevice, 194, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v14);
      }
      if ( v19 || v11 )
      {
        v15 = *(_QWORD *)(v8 + 56);
        v21[0] = 1;
        v16 = CscStoreSetInformationEntry(v15, 0, 0, 0, 0, v21, 0);
        v14 = (unsigned int)v16;
        if ( v16 < 0 )
        {
          if ( v11 && v20 && v16 == -1073741567 && (v24[0] & 0x400) == 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 195, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            }
            a2 = 1;
            v11 = 0;
            goto LABEL_35;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              196,
              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
              (unsigned int)v16);
          }
        }
      }
      if ( !v7 )
      {
LABEL_39:
        if ( (v19 || v11) && (*(_DWORD *)(v8 + 4) & 0x800) != 0 )
          CscClearVNetRootLogicalViewCache(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 48LL), v12, v13, v14, v18);
        CscForceFcbStoreEntryClosed((__int64)a1, a2);
        *(_DWORD *)(v8 + 4) |= 0x4000u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 198, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v5);
        }
        return RxReleaseFcbPagingInMRx(a1, v5);
      }
LABEL_35:
      v22 = 0x1000000000LL;
      v17 = CscStoreSetInformationEntry(*(_QWORD *)(v8 + 56), (__int64)&v22, 0, 0, 0, 0, 0);
      if ( v17 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          197,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          (unsigned int)v17);
      }
      goto LABEL_39;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140074c74  mov     [rsp-8+arg_10], rbx
0x140074c79  push    rbp
0x140074c7a  push    rsi
0x140074c7b  push    rdi
0x140074c7c  push    r12
0x140074c7e  push    r13
0x140074c80  push    r14
0x140074c82  push    r15
0x140074c84  lea     rbp, [rsp-27h]
0x140074c89  sub     rsp, 0E0h
0x140074c90  mov     rax, cs:__security_cookie
0x140074c97  xor     rax, rsp
0x140074c9a  mov     [rbp+57h+var_40], rax
0x140074c9e  mov     r12b, dl
0x140074ca1  mov     r15, rcx
0x140074ca4  xor     edx, edx; Val
0x140074ca6  lea     rcx, [rbp+57h+var_90]; void *
0x140074caa  xorps   xmm0, xmm0
0x140074cad  mov     bl, 1
0x140074caf  movups  [rbp+57h+var_C0], xmm0
0x140074cb3  lea     r8d, [rdx+50h]; Size
0x140074cb7  call    memset
0x140074cbc  mov     rsi, [r15+38h]
0x140074cc0  lea     rdx, [rbp+57h+var_C0]
0x140074cc4  mov     r13, [r15+48h]
0x140074cc8  xor     r14d, r14d
0x140074ccb  mov     rcx, r15
0x140074cce  mov     [rbp+57h+var_D0], r14b
0x140074cd2  mov     [rbp+57h+var_CF], r14b
0x140074cd6  call    CscGetContexts
0x140074cdb  mov     rdi, qword ptr [rbp+57h+var_C0+8]
0x140074cdf  lea     rax, [rbp+57h+var_CF]
0x140074ce3  mov     [rsp+110h+var_E0], r14
0x140074ce8  lea     r8, [rbp+57h+var_90]
0x140074cec  mov     [rsp+110h+var_E8], rax
0x140074cf1  xor     r9d, r9d
0x140074cf4  lea     rax, [rbp+57h+var_D0]
0x140074cf8  xor     edx, edx
0x140074cfa  mov     rcx, [rdi+38h]
0x140074cfe  mov     [rsp+110h+var_F0], rax
0x140074d03  call    CscStoreQueryInformationEntryEx
0x140074d08  lea     rcx, WPP_GLOBAL_Control
0x140074d0f  test    eax, eax
0x140074d11  js      short loc_140074D51
0x140074d13  cmp     [rdi+20h], r14d
0x140074d17  jnz     short loc_140074D29
0x140074d19  cmp     [rbp+57h+var_D0], r14b
0x140074d1d  jnz     short loc_140074D83
0x140074d1f  mov     eax, [rsi+9Ch]
0x140074d25  test    al, 1
0x140074d27  jnz     short loc_140074D83
0x140074d29  mov     rcx, [rbp+57h+var_40]
0x140074d2d  xor     rcx, rsp; StackCookie
0x140074d30  call    __security_check_cookie
0x140074d35  mov     rbx, [rsp+110h+arg_10]
0x140074d3d  add     rsp, 0E0h
0x140074d44  pop     r15
0x140074d46  pop     r14
0x140074d48  pop     r13
0x140074d4a  pop     r12
0x140074d4c  pop     rdi
0x140074d4d  pop     rsi
0x140074d4e  pop     rbp
0x140074d4f  retn
0x140074d51  mov     r10, cs:WPP_GLOBAL_Control
0x140074d58  cmp     r10, rcx
0x140074d5b  jz      short loc_140074D7E
0x140074d5d  mov     ecx, [r10+2Ch]
0x140074d61  test    cl, 20h
0x140074d64  jz      short loc_140074D7E
0x140074d66  mov     rcx, [r10+18h]
0x140074d6a  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074d71  mov     edx, 0C1h
0x140074d76  mov     r9d, eax
0x140074d79  call    WPP_SF_d
0x140074d7e  mov     bl, r14b
0x140074d81  jmp     short loc_140074D13
0x140074d83  xor     edx, edx
0x140074d85  mov     eax, 0EC21h
0x140074d8a  cmp     [rsi], ax
0x140074d8d  mov     r8d, 2
0x140074d93  mov     rcx, r15
0x140074d96  setz    dl
0x140074d99  inc     edx
0x140074d9b  call    CscNotifyReportChange
0x140074da0  cmp     [rbp+57h+var_D0], r14b
0x140074da4  jnz     short loc_140074DC3
0x140074da6  test    r12b, r12b
0x140074da9  jz      loc_140074EC3
0x140074daf  test    bl, bl
0x140074db1  jz      short loc_140074DC0
0x140074db3  test    dword ptr [rbp+57h+var_90], 400h
0x140074dba  jnz     loc_140074EC3
0x140074dc0  mov     r14b, 1
0x140074dc3  xor     bl, bl
0x140074dc5  mov     r8b, 1
0x140074dc8  mov     rdx, rsi
0x140074dcb  mov     rcx, r15
0x140074dce  call    cs:__imp_RxAcquireExclusiveFcbPagingInMRx
0x140074dd5  nop     dword ptr [rax+rax+00h]
0x140074dda  mov     r10, cs:WPP_GLOBAL_Control
0x140074de1  lea     rax, WPP_GLOBAL_Control
0x140074de8  cmp     r10, rax
0x140074deb  jz      short loc_140074E2A
0x140074ded  mov     eax, [r10+2Ch]
0x140074df1  test    al, 20h
0x140074df3  jz      short loc_140074E2A
0x140074df5  mov     al, r14b
0x140074df8  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074dff  neg     al
0x140074e01  mov     edx, 0C2h
0x140074e06  mov     al, bl
0x140074e08  sbb     cl, cl
0x140074e0a  and     cl, 0Bh
0x140074e0d  add     cl, 4Eh ; 'N'
0x140074e10  neg     al
0x140074e12  mov     byte ptr [rsp+110h+var_F0], cl
0x140074e16  mov     rcx, [r10+18h]
0x140074e1a  sbb     r9b, r9b
0x140074e1d  and     r9b, 0Bh
0x140074e21  add     r9b, 4Eh ; 'N'
0x140074e25  call    WPP_SF_cc
0x140074e2a  cmp     [rbp+57h+var_D0], 0
0x140074e2e  jnz     short loc_140074E38
0x140074e30  test    bl, bl
0x140074e32  jz      loc_140074EF9
0x140074e38  mov     rcx, [rdi+38h]
0x140074e3c  lea     rax, [rbp+57h+var_CE]
0x140074e40  mov     [rsp+110h+var_E0], 0
0x140074e49  xor     r9d, r9d
0x140074e4c  mov     [rsp+110h+var_E8], rax
0x140074e51  xor     r8d, r8d
0x140074e54  xor     edx, edx
0x140074e56  mov     [rsp+110h+var_F0], 0
0x140074e5f  mov     [rbp+57h+var_CE], 1
0x140074e63  call    CscStoreSetInformationEntry
0x140074e68  mov     r9d, eax
0x140074e6b  test    eax, eax
0x140074e6d  jns     loc_140074EF9
0x140074e73  test    bl, bl
0x140074e75  jz      short loc_140074ECA
0x140074e77  cmp     [rbp+57h+var_CF], 0
0x140074e7b  jz      short loc_140074ECA
0x140074e7d  cmp     eax, 0C0000101h
0x140074e82  jnz     short loc_140074ECA
0x140074e84  test    dword ptr [rbp+57h+var_90], 400h
0x140074e8b  jnz     short loc_140074ECA
0x140074e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140074e94  lea     r14, WPP_GLOBAL_Control
0x140074e9b  cmp     rcx, r14
0x140074e9e  jz      short loc_140074EBC
0x140074ea0  mov     eax, [rcx+2Ch]
0x140074ea3  test    al, 20h
0x140074ea5  jz      short loc_140074EBC
0x140074ea7  mov     rcx, [rcx+18h]
0x140074eab  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074eb2  mov     edx, 0C3h
0x140074eb7  call    WPP_SF_
0x140074ebc  mov     r12b, 1
0x140074ebf  xor     bl, bl
0x140074ec1  jmp     short loc_140074F05
0x140074ec3  mov     bl, 1
0x140074ec5  jmp     loc_140074DC5
0x140074eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140074ed1  lea     rax, WPP_GLOBAL_Control
0x140074ed8  cmp     rcx, rax
0x140074edb  jz      short loc_140074EF9
0x140074edd  mov     eax, [rcx+2Ch]
0x140074ee0  test    al, 20h
0x140074ee2  jz      short loc_140074EF9
0x140074ee4  mov     rcx, [rcx+18h]
0x140074ee8  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074eef  mov     edx, 0C4h
0x140074ef4  call    WPP_SF_d
0x140074ef9  test    r14b, r14b
0x140074efc  jz      short loc_140074F73
0x140074efe  lea     r14, WPP_GLOBAL_Control
0x140074f05  mov     [rbp+57h+var_C8], 0
0x140074f0d  lea     rdx, [rbp+57h+var_C8]
0x140074f11  mov     dword ptr [rbp+57h+var_C8+4], 10h
0x140074f18  xor     r9d, r9d
0x140074f1b  mov     rcx, [rdi+38h]
0x140074f1f  xor     r8d, r8d
0x140074f22  mov     [rsp+110h+var_E0], 0
0x140074f2b  mov     [rsp+110h+var_E8], 0
0x140074f34  mov     [rsp+110h+var_F0], 0
0x140074f3d  call    CscStoreSetInformationEntry
0x140074f42  test    eax, eax
0x140074f44  jns     short loc_140074F73
0x140074f46  mov     r10, cs:WPP_GLOBAL_Control
0x140074f4d  cmp     r10, r14
0x140074f50  jz      short loc_140074F73
0x140074f52  mov     ecx, [r10+2Ch]
0x140074f56  test    cl, 20h
0x140074f59  jz      short loc_140074F73
0x140074f5b  mov     rcx, [r10+18h]
0x140074f5f  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074f66  mov     edx, 0C5h
0x140074f6b  mov     r9d, eax
0x140074f6e  call    WPP_SF_d
0x140074f73  cmp     [rbp+57h+var_D0], 0
0x140074f77  jnz     short loc_140074F7D
0x140074f79  test    bl, bl
0x140074f7b  jz      short loc_140074F93
0x140074f7d  test    dword ptr [rdi+4], 800h
0x140074f84  jz      short loc_140074F93
0x140074f86  mov     rcx, [r13+28h]
0x140074f8a  mov     rcx, [rcx+30h]
0x140074f8e  call    CscClearVNetRootLogicalViewCache
0x140074f93  mov     dl, r12b
0x140074f96  mov     rcx, r15
0x140074f99  call    CscForceFcbStoreEntryClosed
0x140074f9e  bts     dword ptr [rdi+4], 0Eh
0x140074fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140074faa  lea     rax, WPP_GLOBAL_Control
0x140074fb1  cmp     rcx, rax
0x140074fb4  jz      short loc_140074FD5
0x140074fb6  mov     eax, [rcx+2Ch]
0x140074fb9  test    al, 20h
0x140074fbb  jz      short loc_140074FD5
0x140074fbd  mov     rcx, [rcx+18h]
0x140074fc1  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074fc8  mov     edx, 0C6h
0x140074fcd  mov     r9, rsi
0x140074fd0  call    WPP_SF_q
0x140074fd5  mov     rdx, rsi
0x140074fd8  mov     rcx, r15
0x140074fdb  call    cs:__imp_RxReleaseFcbPagingInMRx
0x140074fe2  nop     dword ptr [rax+rax+00h]
0x140074fe7  jmp     loc_140074D29
```
