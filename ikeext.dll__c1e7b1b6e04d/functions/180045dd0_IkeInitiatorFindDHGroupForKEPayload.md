# IkeInitiatorFindDHGroupForKEPayload

- ea: `0x180045dd0`
- end: `0x1800460ac`
- name: `IkeInitiatorFindDHGroupForKEPayload`
- size: `732`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180046510`
- `0x1800fbcc4`

## callees

- `0x180045dd0`
- `0x18004890c`
- `0x180050850`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045e68`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045ef6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045f3b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045e68`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045ef6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180045f3b`
- `ntdll!EtwEventWriteTransfer` at `0x18004603d`
- `ntdll!EtwEventWriteTransfer` at `0x18004603d`

## pseudocode

```c
__int64 __fastcall IkeInitiatorFindDHGroupForKEPayload(__int64 LockSemaphore_low, _DWORD *a2)
{
  __int64 v3; // rsi
  _QWORD *v4; // rdi
  __int64 *Value; // rax
  __int64 v6; // r14
  __int64 v7; // rdi
  int v8; // ebx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v10; // rax
  DWORD LockSemaphore; // ecx
  __int64 *v12; // rax
  __int64 v13; // rcx
  DWORD v14; // ecx
  char *v15; // rax
  const WCHAR *v16; // rdx
  __int64 v17; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // ecx
  __int64 result; // rax
  unsigned int *v23; // rdx
  unsigned int *v24; // rax
  int v25; // [rsp+3Ch] [rbp-55h] BYREF
  __int64 v26; // [rsp+40h] [rbp-51h] BYREF
  _DWORD v27[2]; // [rsp+48h] [rbp-49h] BYREF
  __int64 v28; // [rsp+50h] [rbp-41h]
  char *v29; // [rsp+58h] [rbp-39h] BYREF
  int v30; // [rsp+60h] [rbp-31h]
  int v31; // [rsp+64h] [rbp-2Dh]
  void *v32; // [rsp+68h] [rbp-29h]
  int v33; // [rsp+70h] [rbp-21h]
  int v34; // [rsp+74h] [rbp-1Dh]
  __int64 *v35; // [rsp+78h] [rbp-19h]
  __int64 v36; // [rsp+80h] [rbp-11h]
  const WCHAR *v37; // [rsp+88h] [rbp-9h]
  int v38; // [rsp+90h] [rbp-1h]
  int v39; // [rsp+94h] [rbp+3h]
  const char *v40; // [rsp+98h] [rbp+7h]
  __int64 v41; // [rsp+A0h] [rbp+Fh]
  int *v42; // [rsp+A8h] [rbp+17h]
  __int64 v43; // [rsp+B0h] [rbp+1Fh]

  v3 = LockSemaphore_low;
  if ( *(_DWORD *)(LockSemaphore_low + 584) == 1 && *(_DWORD *)(*(_QWORD *)(LockSemaphore_low + 1096) + 388LL) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals
        && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
        && (Value = (__int64 *)TlsGetValue(LockSemaphore_low), v4 = WPP_GLOBAL_Control, Value) )
      {
        v6 = *Value;
      }
      else
      {
        LODWORD(v6) = 0;
      }
      v7 = v4[2];
      v8 = *(_DWORD *)(*(_QWORD *)(v3 + 1096) + 388LL);
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iSL(v7, 10, (unsigned int)WPP_25db70d975553be139d7e5f03cdbe9d4_Traceguids, v6, TlsPeerAddr, v8);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_29;
    v10 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( LockSemaphore != -1 )
      {
        v12 = (__int64 *)TlsGetValue(LockSemaphore);
        if ( v12 )
        {
          v13 = *v12;
          v10 = gIkeExtGlobals;
LABEL_19:
          v26 = v13;
          v35 = &v26;
          v36 = 8;
          if ( !v10 )
            goto LABEL_27;
          v14 = (DWORD)v10[86].LockSemaphore;
          if ( v14 == -1 )
            goto LABEL_27;
          v15 = (char *)TlsGetValue(v14);
          v16 = (const WCHAR *)(v15 + 8);
          if ( !v15 )
            v16 = 0;
          if ( v16 )
          {
            v17 = -1;
            while ( v16[++v17] != 0 )
              ;
            v19 = 2 * v17 + 2;
          }
          else
          {
LABEL_27:
            v16 = &LocaleName;
            v19 = 2;
          }
          v38 = v19;
          v37 = v16;
          v40 = "Use DH group previously provided as retry hint";
          v20 = *(_QWORD *)(v3 + 1096);
          v39 = 0;
          v41 = 47;
          v27[0] = 184549376;
          v21 = *(_DWORD *)(v20 + 388);
          v42 = &v25;
          v27[1] = 4;
          v29 = off_180173280;
          v25 = v21;
          v43 = 4;
          v28 = 0;
          v30 = *(unsigned __int16 *)off_180173280;
          v32 = &unk_180164270;
          v31 = 2;
          v33 = 70;
          v34 = 1;
          EtwEventWriteTransfer(qword_180173298, v27, 0, 0, 6, &v29);
LABEL_29:
          result = *(_QWORD *)(v3 + 1096);
          *a2 = *(_DWORD *)(result + 388);
          return result;
        }
        v10 = gIkeExtGlobals;
      }
    }
    v13 = 0;
    goto LABEL_19;
  }
  v23 = *(unsigned int **)(LockSemaphore_low + 744);
  if ( v23 )
    v24 = &v23[80 * *v23 + 4];
  else
    v24 = *(unsigned int **)(**(_QWORD **)(LockSemaphore_low + 736) + 24LL);
  result = v24[5];
  if ( (_DWORD)result )
    *a2 = result;
  return result;
}

```

## disassembly

```asm
0x180045dd0  mov     r11, rsp
0x180045dd3  push    rbp
0x180045dd4  push    rsi
0x180045dd5  push    r15
0x180045dd7  lea     rbp, [r11-5Fh]
0x180045ddb  sub     rsp, 0D0h
0x180045de2  mov     rax, cs:__security_cookie
0x180045de9  xor     rax, rsp
0x180045dec  mov     [rbp+57h+var_30], rax
0x180045df0  cmp     dword ptr [rcx+248h], 1
0x180045df7  mov     r15, rdx
0x180045dfa  mov     rsi, rcx
0x180045dfd  jnz     loc_18004605D
0x180045e03  mov     rax, [rcx+448h]
0x180045e0a  cmp     dword ptr [rax+184h], 0
0x180045e11  jz      loc_18004605D
0x180045e17  mov     [r11+18h], rdi
0x180045e1b  mov     [r11-20h], r12
0x180045e1f  mov     rdi, cs:WPP_GLOBAL_Control
0x180045e26  lea     rax, WPP_GLOBAL_Control
0x180045e2d  xor     r12d, r12d
0x180045e30  cmp     rdi, rax
0x180045e33  jz      loc_180045EC8
0x180045e39  cmp     byte ptr [rdi+19h], 4
0x180045e3d  jb      loc_180045EC8
0x180045e43  test    byte ptr [rdi+1Ch], 10h
0x180045e47  jz      short loc_180045EC8
0x180045e49  mov     rax, cs:gIkeExtGlobals
0x180045e50  mov     [r11+8], rbx
0x180045e54  mov     [r11-28h], r14
0x180045e58  test    rax, rax
0x180045e5b  jz      short loc_180045E7F
0x180045e5d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045e63  cmp     ecx, 0FFFFFFFFh
0x180045e66  jz      short loc_180045E7F
0x180045e68  call    cs:__imp_TlsGetValue
0x180045e6e  mov     rdi, cs:WPP_GLOBAL_Control
0x180045e75  test    rax, rax
0x180045e78  jz      short loc_180045E7F
0x180045e7a  mov     r14, [rax]
0x180045e7d  jmp     short loc_180045E82
0x180045e7f  mov     r14, r12
0x180045e82  mov     rax, [rsi+448h]
0x180045e89  mov     rdi, [rdi+10h]
0x180045e8d  mov     ebx, [rax+184h]
0x180045e93  call    IkeGetTlsPeerAddr
0x180045e98  mov     edx, 0Ah
0x180045e9d  mov     [rsp+28h], ebx
0x180045ea1  mov     r9, r14
0x180045ea4  mov     [rsp+0E0h+var_C0], rax
0x180045ea9  lea     r8, WPP_25db70d975553be139d7e5f03cdbe9d4_Traceguids
0x180045eb0  mov     rcx, rdi
0x180045eb3  call    WPP_SF_iSL
0x180045eb8  mov     r14, [rsp+0E0h+var_20]
0x180045ec0  mov     rbx, [rsp+0E0h+arg_0]
0x180045ec8  mov     eax, cs:dword_180173278
0x180045ece  mov     rdi, [rsp+0E0h+arg_10]
0x180045ed6  cmp     eax, 4
0x180045ed9  jbe     loc_180046043
0x180045edf  mov     rax, cs:gIkeExtGlobals
0x180045ee6  test    rax, rax
0x180045ee9  jz      short loc_180045F14
0x180045eeb  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045ef1  cmp     ecx, 0FFFFFFFFh
0x180045ef4  jz      short loc_180045F14
0x180045ef6  call    cs:__imp_TlsGetValue
0x180045efc  test    rax, rax
0x180045eff  jz      short loc_180045F0D
0x180045f01  mov     rcx, [rax]
0x180045f04  mov     rax, cs:gIkeExtGlobals
0x180045f0b  jmp     short loc_180045F17
0x180045f0d  mov     rax, cs:gIkeExtGlobals
0x180045f14  mov     rcx, r12
0x180045f17  mov     [rbp+57h+var_A8], rcx
0x180045f1b  lea     rcx, [rbp+57h+var_A8]
0x180045f1f  mov     [rbp+57h+var_70], rcx
0x180045f23  mov     [rbp+57h+var_68], 8
0x180045f2b  test    rax, rax
0x180045f2e  jz      short loc_180045F75
0x180045f30  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180045f36  cmp     ecx, 0FFFFFFFFh
0x180045f39  jz      short loc_180045F75
0x180045f3b  call    cs:__imp_TlsGetValue
0x180045f41  test    rax, rax
0x180045f44  lea     rdx, [rax+8]
0x180045f48  cmovz   rdx, r12
0x180045f4c  test    rdx, rdx
0x180045f4f  jz      short loc_180045F75
0x180045f51  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180045f58  nop     dword ptr [rax+rax+00000000h]
0x180045f60  cmp     [rdx+rax*2+2], r12w
0x180045f66  lea     rax, [rax+1]
0x180045f6a  jnz     short loc_180045F60
0x180045f6c  lea     eax, ds:2[rax*2]
0x180045f73  jmp     short loc_180045F81
0x180045f75  lea     rdx, LocaleName
0x180045f7c  mov     eax, 2
0x180045f81  mov     [rbp+57h+var_58], eax
0x180045f84  xor     r9d, r9d
0x180045f87  mov     [rbp+57h+var_60], rdx
0x180045f8b  lea     rax, aUseDhGroupPrev; "Use DH group previously provided as ret"...
0x180045f92  mov     [rbp+57h+var_50], rax
0x180045f96  lea     rdx, [rbp+57h+var_A0]
0x180045f9a  mov     rax, [rsi+448h]
0x180045fa1  xor     r8d, r8d
0x180045fa4  mov     [rbp+57h+var_54], r12d
0x180045fa8  mov     [rbp+57h+var_48], 2Fh ; '/'
0x180045fb0  mov     [rbp+57h+var_A0], 0B000000h
0x180045fb7  mov     ecx, [rax+184h]
0x180045fbd  lea     rax, [rbp+57h+var_AC]
0x180045fc1  mov     [rbp+57h+var_40], rax
0x180045fc5  movzx   eax, cs:word_180164266
0x180045fcc  mov     [rbp+57h+var_9C], eax
0x180045fcf  mov     rax, cs:off_180173280
0x180045fd6  mov     [rbp+57h+var_90], rax
0x180045fda  mov     [rbp+57h+var_AC], ecx
0x180045fdd  lea     rcx, _TraceLoggingMetadata
0x180045fe4  mov     [rbp+57h+var_38], 4
0x180045fec  mov     [rbp+57h+var_98], r12
0x180045ff0  movzx   eax, word ptr [rax]
0x180045ff3  mov     [rbp+57h+var_88], eax
0x180045ff6  lea     rax, unk_180164270
0x180045ffd  mov     [rbp+57h+var_80], rax
0x180046001  lea     rax, _TraceLoggingMetadataEnd
0x180046008  sub     eax, ecx
0x18004600a  mov     [rbp+57h+var_84], 2
0x180046011  mov     [rbp+57h+var_78], 46h ; 'F'
0x180046018  mov     [rbp+57h+var_74], 1
0x18004601f  mov     [rbp+57h+var_B0], eax
0x180046022  mov     eax, [rbp+57h+var_B0]
0x180046025  mov     rcx, cs:qword_180173298
0x18004602c  lea     rax, [rbp+57h+var_90]
0x180046030  mov     [rsp+28h], rax
0x180046035  mov     dword ptr [rsp+0E0h+var_C0], 6
0x18004603d  call    cs:__imp_EtwEventWriteTransfer
0x180046043  mov     rax, [rsi+448h]
0x18004604a  mov     r12, [rsp+0C8h]
0x180046052  mov     ecx, [rax+184h]
0x180046058  mov     [r15], ecx
0x18004605b  jmp     short loc_180046094
0x18004605d  mov     rdx, [rcx+2E8h]
0x180046064  test    rdx, rdx
0x180046067  jz      short loc_18004607C
0x180046069  mov     eax, [rdx]
0x18004606b  lea     rax, [rax+rax*4]
0x18004606f  shl     rax, 6
0x180046073  add     rax, 10h
0x180046077  add     rax, rdx
0x18004607a  jmp     short loc_18004608A
0x18004607c  mov     rax, [rcx+2E0h]
0x180046083  mov     rcx, [rax]
0x180046086  mov     rax, [rcx+18h]
0x18004608a  mov     eax, [rax+14h]
0x18004608d  test    eax, eax
0x18004608f  jz      short loc_180046094
0x180046091  mov     [r15], eax
0x180046094  mov     rcx, [rbp+57h+var_30]
0x180046098  xor     rcx, rsp; StackCookie
0x18004609b  call    __security_check_cookie
0x1800460a0  add     rsp, 0D0h
0x1800460a7  pop     r15
0x1800460a9  pop     rsi
0x1800460aa  pop     rbp
0x1800460ab  retn
```
