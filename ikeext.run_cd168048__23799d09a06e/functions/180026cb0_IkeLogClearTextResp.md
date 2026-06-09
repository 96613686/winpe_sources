# IkeLogClearTextResp

- ea: `0x180026cb0`
- end: `0x180027007`
- name: `IkeLogClearTextResp`
- size: `855`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800217a0`

## callees

- `0x1800037c4`
- `0x180026cb0`
- `0x180050850`
- `0x180060b04`
- `0x1801152c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026d83`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026dbc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026e2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026e7b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026d83`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026dbc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026e2d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180026e7b`
- `ntdll!EtwEventWriteTransfer` at `0x180026fc0`
- `ntdll!EtwEventWriteTransfer` at `0x180026fc0`

## pseudocode

```c
void *__fastcall IkeLogClearTextResp(__int64 a1, __int64 a2, __int64 a3)
{
  void *result; // rax
  int v4; // r14d
  _QWORD *v5; // rcx
  const char *v6; // rdi
  const char *v7; // rbx
  LPCRITICAL_SECTION v8; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v11; // r8
  __int64 v12; // rsi
  DWORD v13; // eax
  __int64 *v14; // rax
  __int64 v15; // r9
  LPCRITICAL_SECTION v16; // rax
  DWORD v17; // ecx
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rbx
  DWORD v21; // ecx
  char *v22; // rax
  const WCHAR *v23; // rdx
  __int64 v24; // rax
  bool v25; // zf
  int v26; // eax
  __int64 v27; // rax
  const WCHAR *v28; // rax
  int v29; // ebx
  _BYTE v30[40]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v32[2]; // [rsp+78h] [rbp-90h] BYREF
  char *v33; // [rsp+88h] [rbp-80h] BYREF
  int v34; // [rsp+90h] [rbp-78h]
  int v35; // [rsp+94h] [rbp-74h]
  char *v36; // [rsp+98h] [rbp-70h]
  int v37; // [rsp+A0h] [rbp-68h]
  int v38; // [rsp+A4h] [rbp-64h]
  __int64 *v39; // [rsp+A8h] [rbp-60h]
  __int64 v40; // [rsp+B0h] [rbp-58h]
  const WCHAR *v41; // [rsp+B8h] [rbp-50h]
  int v42; // [rsp+C0h] [rbp-48h]
  int v43; // [rsp+C4h] [rbp-44h]
  const char *v44; // [rsp+C8h] [rbp-40h]
  __int64 v45; // [rsp+D0h] [rbp-38h]
  const char *v46; // [rsp+D8h] [rbp-30h]
  int v47; // [rsp+E0h] [rbp-28h]
  int v48; // [rsp+E4h] [rbp-24h]
  const WCHAR *v49; // [rsp+E8h] [rbp-20h]
  int v50; // [rsp+F0h] [rbp-18h]
  int v51; // [rsp+F4h] [rbp-14h]

  result = WPP_GLOBAL_Control;
  memset(&v30[8], 0, 32);
  v4 = a1;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WfpIPsecPktTuplesPrint(a1, &v30[8], a3, a2);
    v5 = WPP_GLOBAL_Control;
    v6 = "IKE";
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( v4 )
      {
        v7 = "IKEv2";
        if ( v4 != 2 )
          v7 = "AUTHIP";
      }
      else
      {
        v7 = "IKE";
      }
      v8 = gIkeExtGlobals;
      if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
      {
        v11 = 0;
      }
      else
      {
        Value = TlsGetValue(LockSemaphore);
        v5 = WPP_GLOBAL_Control;
        v11 = Value;
        v8 = gIkeExtGlobals;
      }
      v12 = (__int64)v11 + 8;
      if ( !v11 )
        v12 = 0;
      if ( v8
        && (v13 = (DWORD)v8[86].LockSemaphore, v13 != -1)
        && (v14 = (__int64 *)TlsGetValue(v13), v5 = WPP_GLOBAL_Control, v14) )
      {
        v15 = *v14;
      }
      else
      {
        LODWORD(v15) = 0;
      }
      WPP_SF_iSsS(
        v5[2],
        15,
        (unsigned int)WPP_cc00778c82d836298410d94d06f43a3d_Traceguids,
        v15,
        v12,
        (__int64)v7,
        *(__int64 *)&v30[8]);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      return (void *)WfpMemFree(&v30[8]);
    v16 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v17 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v17 != -1 )
      {
        v18 = (__int64 *)TlsGetValue(v17);
        if ( v18 )
        {
          v19 = *v18;
          v16 = gIkeExtGlobals;
LABEL_28:
          v31 = v19;
          v39 = &v31;
          v20 = -1;
          v40 = 8;
          if ( !v16 )
            goto LABEL_36;
          v21 = (DWORD)v16[86].LockSemaphore;
          if ( v21 == -1 )
            goto LABEL_36;
          v22 = (char *)TlsGetValue(v21);
          v23 = (const WCHAR *)(v22 + 8);
          if ( !v22 )
            v23 = 0;
          if ( v23 )
          {
            v24 = -1;
            do
              v25 = v23[++v24] == 0;
            while ( !v25 );
            v26 = 2 * v24 + 2;
          }
          else
          {
LABEL_36:
            v23 = &LocaleName;
            v26 = 2;
          }
          v42 = v26;
          v44 = "Received clear-text response notification";
          v41 = v23;
          v43 = 0;
          v45 = 42;
          if ( v4 )
          {
            v6 = "IKEv2";
            if ( v4 != 2 )
              v6 = "AUTHIP";
          }
          v27 = -1;
          do
            ++v27;
          while ( v6[v27] );
          v46 = v6;
          v47 = v27 + 1;
          v28 = *(const WCHAR **)&v30[8];
          v48 = 0;
          if ( *(_QWORD *)&v30[8] )
          {
            do
              v25 = *(_WORD *)(*(_QWORD *)&v30[8] + 2 * v20++ + 2) == 0;
            while ( !v25 );
            v29 = 2 * v20 + 2;
          }
          else
          {
            v28 = &LocaleName;
            v29 = 2;
          }
          v49 = v28;
          v33 = off_180173280;
          v50 = v29;
          v51 = 0;
          v32[0] = 0x40B000000LL;
          v32[1] = 0;
          v34 = *(unsigned __int16 *)off_180173280;
          v36 = byte_18014FEA9;
          v35 = 2;
          v37 = 78;
          v38 = 1;
          EtwEventWriteTransfer(qword_180173298, v32, 0, 0, 7, &v33);
          return (void *)WfpMemFree(&v30[8]);
        }
        v16 = gIkeExtGlobals;
      }
    }
    v19 = 0;
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x180026cb0  mov     r11, rsp
0x180026cb3  push    rbp
0x180026cb4  push    r14
0x180026cb6  lea     rbp, [r11-28h]
0x180026cba  sub     rsp, 118h
0x180026cc1  mov     rax, cs:__security_cookie
0x180026cc8  xor     rax, rsp
0x180026ccb  mov     [rbp+20h+var_30], rax
0x180026ccf  mov     rax, cs:WPP_GLOBAL_Control
0x180026cd6  xorps   xmm0, xmm0
0x180026cd9  movups  [rsp+120h+var_E0+8], xmm0
0x180026cde  mov     r14d, ecx
0x180026ce1  movups  [rsp+120h+var_D0+8], xmm0
0x180026ce6  cmp     byte ptr [rax+19h], 4
0x180026cea  jb      loc_180026FF0
0x180026cf0  mov     [r11-18h], rdi
0x180026cf4  mov     r9, rdx
0x180026cf7  mov     [r11-20h], r12
0x180026cfb  lea     rdx, [rsp+120h+var_E0+8]
0x180026d00  mov     [r11-28h], r15
0x180026d04  mov     [r11+8], rbx
0x180026d08  call    WfpIPsecPktTuplesPrint
0x180026d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d14  lea     rax, WPP_GLOBAL_Control
0x180026d1b  xor     r15d, r15d
0x180026d1e  lea     rdi, aIke_1; "IKE"
0x180026d25  lea     r12, aAuthip_0; "AUTHIP"
0x180026d2c  cmp     rcx, rax
0x180026d2f  jz      loc_180026E07
0x180026d35  cmp     byte ptr [rcx+19h], 4
0x180026d39  jb      loc_180026E07
0x180026d3f  test    byte ptr [rcx+1Ch], 10h
0x180026d43  jz      loc_180026E07
0x180026d49  mov     [rsp+120h+arg_10], rsi
0x180026d51  test    r14d, r14d
0x180026d54  jnz     short loc_180026D5B
0x180026d56  mov     rbx, rdi
0x180026d59  jmp     short loc_180026D6A
0x180026d5b  cmp     r14d, 2
0x180026d5f  lea     rbx, aIkev2_1; "IKEv2"
0x180026d66  cmovnz  rbx, r12
0x180026d6a  mov     rdx, cs:gIkeExtGlobals
0x180026d71  test    rdx, rdx
0x180026d74  jz      short loc_180026D9C
0x180026d76  mov     eax, [rdx+0D88h]
0x180026d7c  cmp     eax, 0FFFFFFFFh
0x180026d7f  jz      short loc_180026D9C
0x180026d81  mov     ecx, eax; dwTlsIndex
0x180026d83  call    cs:__imp_TlsGetValue
0x180026d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d90  mov     r8, rax
0x180026d93  mov     rdx, cs:gIkeExtGlobals
0x180026d9a  jmp     short loc_180026D9F
0x180026d9c  mov     r8, r15
0x180026d9f  test    r8, r8
0x180026da2  lea     rsi, [r8+8]
0x180026da6  cmovz   rsi, r15
0x180026daa  test    rdx, rdx
0x180026dad  jz      short loc_180026DD3
0x180026daf  mov     eax, [rdx+0D88h]
0x180026db5  cmp     eax, 0FFFFFFFFh
0x180026db8  jz      short loc_180026DD3
0x180026dba  mov     ecx, eax; dwTlsIndex
0x180026dbc  call    cs:__imp_TlsGetValue
0x180026dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dc9  test    rax, rax
0x180026dcc  jz      short loc_180026DD3
0x180026dce  mov     r9, [rax]
0x180026dd1  jmp     short loc_180026DD6
0x180026dd3  mov     r9, r15
0x180026dd6  mov     rax, qword ptr [rsp+120h+var_E0+8]
0x180026ddb  lea     r8, WPP_cc00778c82d836298410d94d06f43a3d_Traceguids
0x180026de2  mov     rcx, [rcx+10h]
0x180026de6  mov     edx, 0Fh
0x180026deb  mov     [rsp+30h], rax
0x180026df0  mov     [rsp+120h+var_F8], rbx
0x180026df5  mov     [rsp+120h+var_100], rsi
0x180026dfa  call    WPP_SF_iSsS
0x180026dff  mov     rsi, [rsp+120h+arg_10]
0x180026e07  mov     eax, cs:dword_180173278
0x180026e0d  cmp     eax, 4
0x180026e10  jbe     loc_180026FC6
0x180026e16  mov     rax, cs:gIkeExtGlobals
0x180026e1d  test    rax, rax
0x180026e20  jz      short loc_180026E4B
0x180026e22  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180026e28  cmp     ecx, 0FFFFFFFFh
0x180026e2b  jz      short loc_180026E4B
0x180026e2d  call    cs:__imp_TlsGetValue
0x180026e33  test    rax, rax
0x180026e36  jz      short loc_180026E44
0x180026e38  mov     rcx, [rax]
0x180026e3b  mov     rax, cs:gIkeExtGlobals
0x180026e42  jmp     short loc_180026E4E
0x180026e44  mov     rax, cs:gIkeExtGlobals
0x180026e4b  mov     rcx, r15
0x180026e4e  mov     qword ptr [rsp+120h+var_B8], rcx
0x180026e53  lea     rcx, [rsp+120h+var_B8]
0x180026e58  mov     [rbp+20h+var_80], rcx
0x180026e5c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180026e63  mov     [rbp+20h+var_78], 8
0x180026e6b  test    rax, rax
0x180026e6e  jz      short loc_180026EA9
0x180026e70  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180026e76  cmp     ecx, 0FFFFFFFFh
0x180026e79  jz      short loc_180026EA9
0x180026e7b  call    cs:__imp_TlsGetValue
0x180026e81  test    rax, rax
0x180026e84  lea     rdx, [rax+8]
0x180026e88  cmovz   rdx, r15
0x180026e8c  test    rdx, rdx
0x180026e8f  jz      short loc_180026EA9
0x180026e91  mov     rax, rbx
0x180026e94  cmp     [rdx+rax*2+2], r15w
0x180026e9a  lea     rax, [rax+1]
0x180026e9e  jnz     short loc_180026E94
0x180026ea0  lea     eax, ds:2[rax*2]
0x180026ea7  jmp     short loc_180026EB5
0x180026ea9  lea     rdx, LocaleName
0x180026eb0  mov     eax, 2
0x180026eb5  mov     [rbp+20h+var_68], eax
0x180026eb8  lea     rax, aReceivedClearT; "Received clear-text response notificati"...
0x180026ebf  mov     [rbp+20h+var_60], rax
0x180026ec3  mov     [rbp+20h+var_70], rdx
0x180026ec7  mov     [rbp+20h+var_64], r15d
0x180026ecb  mov     [rbp+20h+var_58], 2Ah ; '*'
0x180026ed3  test    r14d, r14d
0x180026ed6  jz      short loc_180026EE7
0x180026ed8  cmp     r14d, 2
0x180026edc  lea     rdi, aIkev2_1; "IKEv2"
0x180026ee3  cmovnz  rdi, r12
0x180026ee7  mov     rax, rbx
0x180026eea  nop     word ptr [rax+rax+00h]
0x180026ef0  inc     rax
0x180026ef3  cmp     [rdi+rax], r15b
0x180026ef7  jnz     short loc_180026EF0
0x180026ef9  inc     eax
0x180026efb  mov     [rbp+20h+var_50], rdi
0x180026eff  mov     [rbp+20h+var_48], eax
0x180026f02  mov     rax, qword ptr [rsp+120h+var_E0+8]
0x180026f07  mov     [rbp+20h+var_44], r15d
0x180026f0b  test    rax, rax
0x180026f0e  jz      short loc_180026F25
0x180026f10  cmp     [rax+rbx*2+2], r15w
0x180026f16  lea     rbx, [rbx+1]
0x180026f1a  jnz     short loc_180026F10
0x180026f1c  lea     ebx, ds:2[rbx*2]
0x180026f23  jmp     short loc_180026F31
0x180026f25  lea     rax, LocaleName
0x180026f2c  mov     ebx, 2
0x180026f31  mov     [rbp+20h+var_40], rax
0x180026f35  lea     rcx, _TraceLoggingMetadata
0x180026f3c  movzx   eax, cs:word_18014FE9F
0x180026f43  lea     rdx, [rsp+120h+var_B0]
0x180026f48  mov     dword ptr [rsp+120h+var_B0+4], eax
0x180026f4c  xor     r9d, r9d
0x180026f4f  mov     rax, cs:off_180173280
0x180026f56  xor     r8d, r8d
0x180026f59  mov     [rbp+20h+var_A0], rax
0x180026f5d  mov     [rbp+20h+var_38], ebx
0x180026f60  mov     [rbp+20h+var_34], r15d
0x180026f64  mov     dword ptr [rsp+120h+var_B0], 0B000000h
0x180026f6c  mov     [rsp+78h], r15
0x180026f71  movzx   eax, word ptr [rax]
0x180026f74  mov     [rbp+20h+var_98], eax
0x180026f77  lea     rax, byte_18014FEA9
0x180026f7e  mov     [rbp+20h+var_90], rax
0x180026f82  lea     rax, _TraceLoggingMetadataEnd
0x180026f89  sub     eax, ecx
0x180026f8b  mov     [rbp+20h+var_94], 2
0x180026f92  mov     [rbp+20h+var_88], 4Eh ; 'N'
0x180026f99  mov     [rbp+20h+var_84], 1
0x180026fa0  mov     dword ptr [rsp+120h+var_E0], eax
0x180026fa4  mov     eax, dword ptr [rsp+120h+var_E0]
0x180026fa8  mov     rcx, cs:qword_180173298
0x180026faf  lea     rax, [rbp+20h+var_A0]
0x180026fb3  mov     [rsp+120h+var_F8], rax
0x180026fb8  mov     dword ptr [rsp+120h+var_100], 7
0x180026fc0  call    cs:__imp_EtwEventWriteTransfer
0x180026fc6  lea     rcx, [rsp+120h+var_E0+8]
0x180026fcb  call    WfpMemFree
0x180026fd0  mov     r15, [rsp+120h+var_20]
0x180026fd8  mov     r12, [rsp+120h+var_18]
0x180026fe0  mov     rdi, [rsp+110h]
0x180026fe8  mov     rbx, [rsp+120h+arg_0]
0x180026ff0  mov     rcx, [rbp+20h+var_30]
0x180026ff4  xor     rcx, rsp; StackCookie
0x180026ff7  call    __security_check_cookie
0x180026ffc  add     rsp, 118h
0x180027003  pop     r14
0x180027005  pop     rbp
0x180027006  retn
```
