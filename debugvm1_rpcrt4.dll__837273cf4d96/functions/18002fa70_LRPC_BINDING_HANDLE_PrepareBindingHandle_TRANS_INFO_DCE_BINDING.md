# LRPC_BINDING_HANDLE::PrepareBindingHandle(TRANS_INFO *,DCE_BINDING *)

- ea: `0x18002fa70`
- end: `0x18002fd74`
- name: `?PrepareBindingHandle@LRPC_BINDING_HANDLE@@UEAAJPEAVTRANS_INFO@@PEAVDCE_BINDING@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE *__hidden this, struct TRANS_INFO *, struct DCE_BINDING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021e18`
- `0x1800274e0`
- `0x1800283bc`
- `0x18002e0f0`
- `0x18002eca0`
- `0x18002fa70`
- `0x18002fd80`
- `0x18009e1a0`
- `0x1800ca140`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002fc9e`
- `ntdll!RtlLeaveCriticalSection` at `0x18002fc9e`
- `ntdll!RtlEnterCriticalSection` at `0x18002fc0f`
- `ntdll!RtlEnterCriticalSection` at `0x18002fc0f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fd1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002fd1d`

## pseudocode

```c
__int64 __fastcall LRPC_BINDING_HANDLE::PrepareBindingHandle(
        LRPC_BINDING_HANDLE *this,
        struct TRANS_INFO *a2,
        struct DCE_BINDING *a3)
{
  unsigned __int16 *v3; // rdi
  _WORD *v6; // rcx
  _WORD *v7; // rax
  unsigned int i; // ecx
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v13; // edi
  char v14; // [rsp+90h] [rbp-80h] BYREF
  char v15; // [rsp+98h] [rbp-78h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-70h] BYREF
  int v17; // [rsp+A8h] [rbp-68h]
  LRPC_BINDING_HANDLE *v18; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+B8h] [rbp-58h] BYREF
  char v20[16]; // [rsp+C0h] [rbp-50h] BYREF
  char *v21; // [rsp+D0h] [rbp-40h]
  __int64 v22; // [rsp+D8h] [rbp-38h]
  char *v23; // [rsp+E0h] [rbp-30h]
  __int64 v24; // [rsp+E8h] [rbp-28h]
  LRPC_BINDING_HANDLE **v25; // [rsp+F0h] [rbp-20h]
  __int64 v26; // [rsp+F8h] [rbp-18h]
  __int64 *v27; // [rsp+100h] [rbp-10h]
  __int64 v28; // [rsp+108h] [rbp-8h]
  __int64 *v29; // [rsp+110h] [rbp+0h]
  __int64 v30; // [rsp+118h] [rbp+8h]

  v3 = (unsigned __int16 *)*((_QWORD *)a3 + 1);
  v16 = 0;
  v17 = 0;
  if ( v3 && *v3 && CompareStringW(0x7Fu, 1u, v3, -1, gLocalComputerName, -1) != 2 )
  {
    RpcpErrorAddRecord(2u, 1707, 0x3A3u, v3, (unsigned __int16 *)gLocalComputerName);
    return 1707;
  }
  v6 = (_WORD *)*((_QWORD *)a3 + 3);
  if ( v6 && *v6 )
  {
    v11 = I_RpcParseSecurity(v6, &v16);
    v12 = v11;
    if ( v11 )
    {
      RpcpErrorAddRecord(2u, v11, 0x3A2u, 0, 0);
      return v12;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    v13 = 3;
    if ( HIDWORD(v16) <= 3 )
      v13 = dword_1800E2D98[SHIDWORD(v16)];
    LRPC_BINDING_HANDLE::Unbind(this, 1);
    v12 = LRPC_BASE_BINDING_HANDLE::SetAuthInformation(
            this,
            0,
            6u,
            10,
            0,
            0,
            0,
            0,
            v13,
            (unsigned __int8)v17,
            0,
            1u,
            0,
            0,
            0,
            BYTE1(v17),
            0,
            0);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 304));
    if ( v12 )
      return v12;
  }
  *((_QWORD *)this + 77) = a3;
  v7 = (_WORD *)*((_QWORD *)a3 + 2);
  if ( v7 && *v7 )
  {
    if ( dword_1800F9624 )
    {
      for ( i = 0; i < 4; ++i )
      {
        if ( `LogEventToEtw'::`2'::EtwEventSubjectFilter[i] == 104 )
          goto LABEL_13;
      }
      if ( (Microsoft_Windows_RPCEnableBits & 8) != 0 )
      {
        v10 = (int)(*((_DWORD *)this + 99) << 16);
        v21 = &v14;
        v16 = v10 | 4;
        v23 = &v15;
        v26 = 8;
        v25 = &v18;
        v27 = &v19;
        v29 = &v16;
        v28 = 8;
        v30 = 8;
        v19 = 34;
        v18 = this;
        v15 = 61;
        v14 = 104;
        v22 = 1;
        v24 = 1;
        McGenEventWrite_EtwEventWriteTransfer(&RpcEtwGuid_Context, (__int64)RPCLogEvent, (__int64)a3, 6, (__int64)v20);
      }
    }
LABEL_13:
    *((_DWORD *)this + 99) = 4;
  }
  else
  {
    if ( dword_1800F9624 )
      LogEventToEtw(0x68u, 0x3Du, (__int64)this, 34, (int)(*((_DWORD *)this + 99) << 16) | 1LL);
    *((_DWORD *)this + 99) = 1;
    *((_DWORD *)this + 124) |= 0x10u;
  }
  return 0;
}

```

## disassembly

```asm
0x18002fa70  mov     [rsp-8+arg_8], rbx
0x18002fa75  push    rbp
0x18002fa76  push    rsi
0x18002fa77  push    rdi
0x18002fa78  push    r12
0x18002fa7a  push    r13
0x18002fa7c  push    r14
0x18002fa7e  push    r15
0x18002fa80  lea     rbp, [rsp-20h]
0x18002fa85  sub     rsp, 130h
0x18002fa8c  mov     rax, cs:__security_cookie
0x18002fa93  xor     rax, rsp
0x18002fa96  mov     [rbp+50h+var_40], rax
0x18002fa9a  mov     rdi, [r8+8]
0x18002fa9e  xor     eax, eax
0x18002faa0  xor     r15d, r15d
0x18002faa3  mov     [rbp+50h+var_C0], rax
0x18002faa7  mov     [rbp+50h+var_B8], eax
0x18002faaa  mov     rsi, r8
0x18002faad  mov     rbx, rcx
0x18002fab0  lea     r12d, [rax+1]
0x18002fab4  lea     r14d, [rax+2]
0x18002fab8  test    rdi, rdi
0x18002fabb  jz      short loc_18002FAC7
0x18002fabd  cmp     [rdi], r15w
0x18002fac1  jnz     loc_18002FCFD
0x18002fac7  mov     rcx, [rsi+18h]
0x18002facb  lea     r13, __ImageBase
0x18002fad2  test    rcx, rcx
0x18002fad5  jnz     loc_18002FBE8
0x18002fadb  mov     [rbx+268h], rsi
0x18002fae2  mov     rax, [rsi+10h]
0x18002fae6  test    rax, rax
0x18002fae9  jz      loc_18002FCB3
0x18002faef  cmp     [rax], r15w
0x18002faf3  jz      loc_18002FCB3
0x18002faf9  cmp     cs:dword_1800F9624, r15d
0x18002fb00  jz      short loc_18002FB2A
0x18002fb02  mov     ecx, r15d
0x18002fb05  cmp     ecx, 4
0x18002fb08  jnb     short loc_18002FB1D
0x18002fb0a  movsxd  rax, ecx
0x18002fb0d  cmp     byte ptr [rax+r13+0E1808h], 68h ; 'h'
0x18002fb16  jz      short loc_18002FB2A
0x18002fb18  add     ecx, r12d
0x18002fb1b  jmp     short loc_18002FB05
0x18002fb1d  mov     edx, 8
0x18002fb22  test    cs:Microsoft_Windows_RPCEnableBits, dl
0x18002fb28  jnz     short loc_18002FB5D
0x18002fb2a  mov     dword ptr [rbx+18Ch], 4
0x18002fb34  xor     eax, eax
0x18002fb36  mov     rcx, [rbp+50h+var_40]
0x18002fb3a  xor     rcx, rsp; StackCookie
0x18002fb3d  call    __security_check_cookie
0x18002fb42  mov     rbx, [rsp+160h+arg_8]
0x18002fb4a  add     rsp, 130h
0x18002fb51  pop     r15
0x18002fb53  pop     r14
0x18002fb55  pop     r13
0x18002fb57  pop     r12
0x18002fb59  pop     rdi
0x18002fb5a  pop     rsi
0x18002fb5b  pop     rbp
0x18002fb5c  retn
0x18002fb5d  mov     eax, [rbx+18Ch]
0x18002fb63  mov     r9d, 6
0x18002fb69  shl     eax, 10h
0x18002fb6c  movsxd  rcx, eax
0x18002fb6f  lea     rax, [rbp+50h+var_D0]
0x18002fb73  mov     [rbp+50h+var_90], rax
0x18002fb77  or      rcx, 4
0x18002fb7b  lea     rax, [rbp+50h+var_C8]
0x18002fb7f  mov     [rbp+50h+var_C0], rcx
0x18002fb83  mov     [rbp+50h+var_80], rax
0x18002fb87  lea     rcx, RpcEtwGuid_Context
0x18002fb8e  lea     rax, [rbp+50h+var_B0]
0x18002fb92  mov     [rbp+50h+var_68], rdx
0x18002fb96  mov     [rbp+50h+var_70], rax
0x18002fb9a  lea     rax, [rbp+50h+var_A8]
0x18002fb9e  mov     [rbp+50h+var_60], rax
0x18002fba2  lea     rax, [rbp+50h+var_C0]
0x18002fba6  mov     [rbp+50h+var_50], rax
0x18002fbaa  lea     rax, [rbp+50h+var_A0]
0x18002fbae  mov     [rbp+50h+var_58], rdx
0x18002fbb2  mov     [rbp+50h+var_48], rdx
0x18002fbb6  lea     rdx, RPCLogEvent
0x18002fbbd  mov     [rsp+160h+lpString2], rax
0x18002fbc2  mov     [rbp+50h+var_A8], 22h ; '"'
0x18002fbca  mov     [rbp+50h+var_B0], rbx
0x18002fbce  mov     [rbp+50h+var_C8], 3Dh ; '='
0x18002fbd2  mov     [rbp+50h+var_D0], 68h ; 'h'
0x18002fbd6  mov     [rbp+50h+var_88], r12
0x18002fbda  mov     [rbp+50h+var_78], r12
0x18002fbde  call    McGenEventWrite_EtwEventWriteTransfer
0x18002fbe3  jmp     loc_18002FB2A
0x18002fbe8  cmp     [rcx], r15w
0x18002fbec  jz      loc_18002FADB
0x18002fbf2  lea     rdx, [rbp+50h+var_C0]
0x18002fbf6  call    I_RpcParseSecurity
0x18002fbfb  mov     edi, eax
0x18002fbfd  test    eax, eax
0x18002fbff  jnz     loc_18002FD57
0x18002fc05  lea     r14, [rbx+130h]
0x18002fc0c  mov     rcx, r14; CriticalSection
0x18002fc0f  call    cs:__imp_RtlEnterCriticalSection
0x18002fc15  mov     edi, 3
0x18002fc1a  cmp     dword ptr [rbp+50h+var_C0+4], edi
0x18002fc1d  ja      short loc_18002FC2B
0x18002fc1f  movsxd  rax, dword ptr [rbp+50h+var_C0+4]
0x18002fc23  mov     edi, ds:rva dword_1800E2D98[r13+rax*4]
0x18002fc2b  mov     edx, r12d; int
0x18002fc2e  mov     rcx, rbx; this
0x18002fc31  call    ?Unbind@LRPC_BINDING_HANDLE@@UEAAXH@Z; LRPC_BINDING_HANDLE::Unbind(int)
0x18002fc36  movzx   eax, byte ptr [rbp+50h+var_B8+1]
0x18002fc3a  mov     rcx, rbx; this
0x18002fc3d  movzx   edx, byte ptr [rbp+50h+var_B8]
0x18002fc41  mov     [rsp+160h+CreatorDescriptor], r15; CreatorDescriptor
0x18002fc49  mov     [rsp+160h+var_E0], r15d; int
0x18002fc51  mov     [rsp+160h+var_E8], eax; int
0x18002fc55  mov     [rsp+160h+pSourceSid], r15; pSourceSid
0x18002fc5a  mov     [rsp+160h+var_F8], r15; void *
0x18002fc5f  mov     [rsp+160h+var_100], r15d; unsigned int
0x18002fc64  mov     [rsp+160h+var_108], r12d; unsigned int
0x18002fc69  mov     [rsp+160h+var_110], r15d; unsigned int
0x18002fc6e  mov     [rsp+160h+var_118], edx; unsigned int
0x18002fc72  xor     edx, edx; unsigned __int16 *
0x18002fc74  mov     [rsp+160h+var_120], edi; unsigned int
0x18002fc78  mov     [rsp+160h+var_128], r15; struct SECURITY_CREDENTIALS *
0x18002fc7d  mov     [rsp+160h+var_130], r15d; unsigned int
0x18002fc82  lea     r9d, [rdx+0Ah]; unsigned int
0x18002fc86  mov     qword ptr [rsp+160h+cchCount2], r15; void *
0x18002fc8b  lea     r8d, [rdx+6]; unsigned int
0x18002fc8f  mov     [rsp+160h+lpString2], r15; AuthData
0x18002fc94  call    ?SetAuthInformation@LRPC_BASE_BINDING_HANDLE@@UEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1@Z; LRPC_BASE_BINDING_HANDLE::SetAuthInformation(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *)
0x18002fc99  mov     rcx, r14; CriticalSection
0x18002fc9c  mov     edi, eax
0x18002fc9e  call    cs:__imp_RtlLeaveCriticalSection
0x18002fca4  test    edi, edi
0x18002fca6  jz      loc_18002FADB
0x18002fcac  mov     eax, edi
0x18002fcae  jmp     loc_18002FB36
0x18002fcb3  cmp     cs:dword_1800F9624, r15d
0x18002fcba  jz      short loc_18002FCE2
0x18002fcbc  mov     eax, [rbx+18Ch]
0x18002fcc2  mov     r9d, 22h ; '"'; __int64
0x18002fcc8  shl     eax, 10h
0x18002fccb  mov     r8, rbx; __int64
0x18002fcce  movsxd  rcx, eax
0x18002fcd1  mov     dl, 3Dh ; '='; unsigned __int8
0x18002fcd3  or      rcx, r12
0x18002fcd6  mov     [rsp+160h+lpString2], rcx; __int64
0x18002fcdb  mov     cl, 68h ; 'h'; unsigned __int8
0x18002fcdd  call    ?LogEventToEtw@@YAXEE_J00@Z; LogEventToEtw(uchar,uchar,__int64,__int64,__int64)
0x18002fce2  mov     [rbx+18Ch], r12d
0x18002fce9  mov     eax, [rbx+1F0h]
0x18002fcef  or      eax, 10h
0x18002fcf2  mov     [rbx+1F0h], eax
0x18002fcf8  jmp     loc_18002FB34
0x18002fcfd  mov     rax, cs:?gLocalComputerName@@3PEAGEA; ushort * gLocalComputerName
0x18002fd04  or      r9d, 0FFFFFFFFh; cchCount1
0x18002fd08  mov     [rsp+160h+cchCount2], r9d; cchCount2
0x18002fd0d  mov     r8, rdi; lpString1
0x18002fd10  mov     edx, r12d; dwCmpFlags
0x18002fd13  mov     [rsp+160h+lpString2], rax; lpString2
0x18002fd18  mov     ecx, 7Fh; Locale
0x18002fd1d  call    cs:__imp_CompareStringW
0x18002fd23  cmp     eax, r14d
0x18002fd26  jz      loc_18002FAC7
0x18002fd2c  mov     rax, cs:?gLocalComputerName@@3PEAGEA; ushort * gLocalComputerName
0x18002fd33  mov     ebx, 6ABh
0x18002fd38  mov     edx, ebx; int
0x18002fd3a  mov     [rsp+160h+lpString2], rax; unsigned __int16 *
0x18002fd3f  mov     r8d, 3A3h; unsigned __int16
0x18002fd45  mov     r9, rdi; unsigned __int16 *
0x18002fd48  mov     ecx, r14d; unsigned int
0x18002fd4b  call    ?RpcpErrorAddRecord@@YAXKJGPEAG0@Z; RpcpErrorAddRecord(ulong,long,ushort,ushort *,ushort *)
0x18002fd50  mov     eax, ebx
0x18002fd52  jmp     loc_18002FB36
0x18002fd57  mov     r8d, 3A2h; unsigned __int16
0x18002fd5d  mov     [rsp+160h+lpString2], r15; struct tagParam *
0x18002fd62  xor     r9d, r9d; int
0x18002fd65  mov     edx, edi; int
0x18002fd67  mov     ecx, r14d; unsigned int
0x18002fd6a  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x18002fd6f  jmp     loc_18002FCAC
```
