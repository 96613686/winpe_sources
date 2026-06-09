# KapiReceiveKaUpdateRequest

- ea: `0x18000f920`
- end: `0x18000fd7e`
- name: `KapiReceiveKaUpdateRequest`
- size: `1118`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, __int64, __int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800050d0`
- `0x180006eb0`
- `0x1800098f0`
- `0x18000a160`
- `0x18000f920`
- `0x18000fd90`
- `0x18000ffa0`
- `0x18001002c`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f997`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f997`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f9e4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000fd28`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000fd28`

## pseudocode

```c
void __fastcall KapiReceiveKaUpdateRequest(
        struct _RPC_ASYNC_STATE *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  int v8; // esi
  void *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  int v12; // r14d
  struct _RPC_ASYNC_STATE *v13; // r15
  __int64 v14; // rcx
  __int64 v15; // r8
  PVOID *v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // eax
  int v20; // [rsp+30h] [rbp-A9h] BYREF
  int Reply; // [rsp+38h] [rbp-A1h] BYREF
  PRPC_ASYNC_STATE pAsync; // [rsp+40h] [rbp-99h] BYREF
  int v23; // [rsp+48h] [rbp-91h] BYREF
  __int64 v24; // [rsp+50h] [rbp-89h] BYREF
  __int64 v25; // [rsp+58h] [rbp-81h] BYREF
  void *v26; // [rsp+60h] [rbp-79h] BYREF
  char v27[16]; // [rsp+70h] [rbp-69h] BYREF
  __int64 *v28; // [rsp+80h] [rbp-59h]
  __int64 v29; // [rsp+88h] [rbp-51h]
  __int64 *v30; // [rsp+90h] [rbp-49h]
  __int64 v31; // [rsp+98h] [rbp-41h]
  void **v32; // [rsp+A0h] [rbp-39h]
  __int64 v33; // [rsp+A8h] [rbp-31h]
  int *v34; // [rsp+B0h] [rbp-29h]
  __int64 v35; // [rsp+B8h] [rbp-21h]
  int *v36; // [rsp+C0h] [rbp-19h]
  __int64 v37; // [rsp+C8h] [rbp-11h]
  PRPC_ASYNC_STATE *p_pAsync; // [rsp+D0h] [rbp-9h]
  __int64 v39; // [rsp+D8h] [rbp-1h]

  pAsync = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
  }
  v8 = 0;
  *a4 = 0;
  v9 = 0;
  *a5 = 0;
  *a6 = 0;
  Reply = 0;
  v20 = 0;
  EnterCriticalSection(&g_KapiProviderSetLock);
  v10 = KapiLookupProviderByHandle(a3);
  v11 = v10;
  if ( !v10 )
  {
    Reply = 1168;
    v8 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 1168);
    }
LABEL_5:
    v12 = 0;
LABEL_6:
    v13 = pAsync;
    goto LABEL_7;
  }
  if ( *(_QWORD *)(v10 + 24) )
  {
    Reply = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 87);
    }
    v8 = 1;
    goto LABEL_5;
  }
  v17 = MALLOC(0x38u);
  v9 = v17;
  if ( !v17 )
  {
    Reply = 8;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, 8);
    }
    v12 = v20;
    v8 = 1;
    goto LABEL_6;
  }
  v17[3] = a5;
  v13 = pAsync;
  v17[4] = a6;
  v17[5] = v13;
  v17[2] = a4;
  v17[6] = v11;
  v17[1] = v17;
  *v17 = v17;
  v12 = *(_DWORD *)(v11 + 20);
  if ( v12 )
  {
    *(_DWORD *)(v11 + 20) = 0;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0pqsq_EventWriteTransfer(v18, NcbKapiProviderReference, v11, *(unsigned int *)(v11 + 16));
    KapiReferenceProviderEx(v11);
  }
  else
  {
    *(_QWORD *)(v11 + 24) = v17;
    v9 = 0;
  }
LABEL_7:
  LeaveCriticalSection(&g_KapiProviderSetLock);
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    LODWORD(pAsync) = Reply;
    v23 = v8;
    v28 = &v24;
    v30 = &v25;
    v32 = &v26;
    v34 = &v20;
    v36 = &v23;
    p_pAsync = &pAsync;
    v20 = v12;
    v26 = v9;
    v25 = v11;
    v24 = a3;
    v29 = 8;
    v31 = 8;
    v33 = 8;
    v35 = 4;
    v37 = 4;
    v39 = 4;
    McGenEventWrite_EventWriteTransfer(v14, NcbKapiReceiveKaUpdateRequest, v15, 7, v27);
  }
  if ( v9 )
    KapiProcessUpdateRequest(v9);
  if ( !v8 )
    goto LABEL_12;
  v19 = RpcAsyncCompleteCall(v13, &Reply);
  if ( !v19 )
    goto LABEL_12;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids, v19);
LABEL_12:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0pqsq_EventWriteTransfer(v16, NcbKapiProviderDereference, v11, *(unsigned int *)(v11 + 16));
    KapiDereferenceProviderEx((LPVOID)v11);
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 2) != 0 && *((_BYTE *)v16 + 25) >= 6u )
    WPP_SF_(v16[2], 55, &WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids);
}

```

## disassembly

```asm
0x18000f920  mov     [rsp-8+arg_8], rbx
0x18000f925  push    rbp
0x18000f926  push    rsi
0x18000f927  push    rdi
0x18000f928  push    r12
0x18000f92a  push    r13
0x18000f92c  push    r14
0x18000f92e  push    r15
0x18000f930  lea     rbp, [rsp-17h]
0x18000f935  sub     rsp, 0F0h
0x18000f93c  mov     rax, cs:__security_cookie
0x18000f943  xor     rax, rsp
0x18000f946  mov     [rbp+47h+var_40], rax
0x18000f94a  mov     r15, [rbp+47h+arg_20]
0x18000f94e  mov     r14, r9
0x18000f951  mov     r12, [rbp+47h+arg_28]
0x18000f955  mov     r13, r8
0x18000f958  mov     [rsp+120h+pAsync], rcx
0x18000f95d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f964  lea     rax, WPP_GLOBAL_Control
0x18000f96b  cmp     rcx, rax
0x18000f96e  jz      short loc_18000F97A
0x18000f970  test    byte ptr [rcx+1Ch], 2
0x18000f974  jnz     loc_18000FC40
0x18000f97a  xor     esi, esi
0x18000f97c  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18000f983  mov     [r14], rsi
0x18000f986  mov     ebx, esi
0x18000f988  mov     [r15], rsi
0x18000f98b  mov     [r12], rsi
0x18000f98f  mov     [rsp+120h+Reply], esi
0x18000f993  mov     [rsp+120h+var_F0], esi
0x18000f997  call    cs:__imp_EnterCriticalSection
0x18000f99d  mov     rcx, r13
0x18000f9a0  call    KapiLookupProviderByHandle
0x18000f9a5  mov     rdi, rax
0x18000f9a8  test    rax, rax
0x18000f9ab  jnz     loc_18000FA4F
0x18000f9b1  mov     [rsp+120h+Reply], 490h
0x18000f9b9  mov     esi, 1
0x18000f9be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c5  lea     rax, WPP_GLOBAL_Control
0x18000f9cc  cmp     rcx, rax
0x18000f9cf  jnz     loc_18000FC64
0x18000f9d5  mov     r14d, ebx
0x18000f9d8  mov     r15, [rsp+120h+pAsync]
0x18000f9dd  lea     rcx, g_KapiProviderSetLock; lpCriticalSection
0x18000f9e4  call    cs:__imp_LeaveCriticalSection
0x18000f9ea  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000f9f1  jnz     loc_18000FAFA
0x18000f9f7  test    rbx, rbx
0x18000f9fa  jnz     loc_18000FC05
0x18000fa00  test    esi, esi
0x18000fa02  jnz     loc_18000FD20
0x18000fa08  lea     rbx, WPP_GLOBAL_Control
0x18000fa0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa16  test    rdi, rdi
0x18000fa19  jnz     loc_18000FAD9
0x18000fa1f  cmp     rcx, rbx
0x18000fa22  jnz     loc_18000FAAB
0x18000fa28  mov     rcx, [rbp+47h+var_40]
0x18000fa2c  xor     rcx, rsp; StackCookie
0x18000fa2f  call    __security_check_cookie
0x18000fa34  mov     rbx, [rsp+120h+arg_8]
0x18000fa3c  add     rsp, 0F0h
0x18000fa43  pop     r15
0x18000fa45  pop     r14
0x18000fa47  pop     r13
0x18000fa49  pop     r12
0x18000fa4b  pop     rdi
0x18000fa4c  pop     rsi
0x18000fa4d  pop     rbp
0x18000fa4e  retn
0x18000fa4f  cmp     [rax+18h], rbx
0x18000fa53  jnz     loc_18000FBBC
0x18000fa59  mov     ecx, 38h ; '8'; dwBytes
0x18000fa5e  call    MALLOC
0x18000fa63  mov     rbx, rax
0x18000fa66  test    rax, rax
0x18000fa69  jz      loc_18000FC12
0x18000fa6f  mov     [rax+18h], r15
0x18000fa73  mov     r15, [rsp+120h+pAsync]
0x18000fa78  mov     [rax+20h], r12
0x18000fa7c  xor     r12d, r12d
0x18000fa7f  mov     [rax+28h], r15
0x18000fa83  mov     [rax+10h], r14
0x18000fa87  mov     [rax+30h], rdi
0x18000fa8b  mov     [rax+8], rax
0x18000fa8f  mov     [rax], rax
0x18000fa92  mov     r14d, [rdi+14h]
0x18000fa96  test    r14d, r14d
0x18000fa99  jnz     loc_18000FB9E
0x18000fa9f  mov     [rdi+18h], rax
0x18000faa3  mov     ebx, r12d
0x18000faa6  jmp     loc_18000F9DD
0x18000faab  test    byte ptr [rcx+1Ch], 2
0x18000faaf  jz      loc_18000FA28
0x18000fab5  cmp     byte ptr [rcx+19h], 6
0x18000fab9  jb      loc_18000FA28
0x18000fabf  mov     rcx, [rcx+10h]
0x18000fac3  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000faca  mov     edx, 37h ; '7'
0x18000facf  call    WPP_SF_
0x18000fad4  jmp     loc_18000FA28
0x18000fad9  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000fae0  jnz     loc_18000FBE5
0x18000fae6  mov     rcx, rdi
0x18000fae9  call    KapiDereferenceProviderEx
0x18000faee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faf5  jmp     loc_18000FA1F
0x18000fafa  mov     eax, [rsp+120h+Reply]
0x18000fafe  lea     rdx, NcbKapiReceiveKaUpdateRequest
0x18000fb05  mov     dword ptr [rsp+120h+pAsync], eax
0x18000fb09  mov     r9d, 7
0x18000fb0f  lea     rax, [rsp+120h+var_D0]
0x18000fb14  mov     [rsp+120h+var_D8], esi
0x18000fb18  mov     [rbp+47h+var_A0], rax
0x18000fb1c  lea     rax, [rsp+120h+var_C8]
0x18000fb21  mov     [rbp+47h+var_90], rax
0x18000fb25  lea     rax, [rbp+47h+var_C0]
0x18000fb29  mov     [rbp+47h+var_80], rax
0x18000fb2d  lea     rax, [rsp+120h+var_F0]
0x18000fb32  mov     [rbp+47h+var_70], rax
0x18000fb36  lea     rax, [rsp+120h+var_D8]
0x18000fb3b  mov     [rbp+47h+var_60], rax
0x18000fb3f  lea     rax, [rsp+120h+pAsync]
0x18000fb44  mov     [rbp+47h+var_50], rax
0x18000fb48  lea     rax, [rbp+47h+var_B0]
0x18000fb4c  mov     [rsp+120h+var_100], rax
0x18000fb51  mov     [rsp+120h+var_F0], r14d
0x18000fb56  mov     [rbp+47h+var_C0], rbx
0x18000fb5a  mov     [rsp+120h+var_C8], rdi
0x18000fb5f  mov     [rsp+120h+var_D0], r13
0x18000fb64  mov     [rbp+47h+var_98], 8
0x18000fb6c  mov     [rbp+47h+var_88], 8
0x18000fb74  mov     [rbp+47h+var_78], 8
0x18000fb7c  mov     [rbp+47h+var_68], 4
0x18000fb84  mov     [rbp+47h+var_58], 4
0x18000fb8c  mov     [rbp+47h+var_48], 4
0x18000fb94  call    McGenEventWrite_EventWriteTransfer
0x18000fb99  jmp     loc_18000F9F7
0x18000fb9e  mov     [rdi+14h], r12d
0x18000fba2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000fba9  jnz     loc_18000FD00
0x18000fbaf  mov     rcx, rdi
0x18000fbb2  call    KapiReferenceProviderEx
0x18000fbb7  jmp     loc_18000F9DD
0x18000fbbc  mov     [rsp+120h+Reply], 57h ; 'W'
0x18000fbc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbcb  lea     rax, WPP_GLOBAL_Control
0x18000fbd2  cmp     rcx, rax
0x18000fbd5  jnz     loc_18000FC98
0x18000fbdb  mov     esi, 1
0x18000fbe0  jmp     loc_18000F9D5
0x18000fbe5  mov     r9d, [rdi+10h]
0x18000fbe9  lea     rdx, NcbKapiProviderDereference
0x18000fbf0  mov     r8, rdi
0x18000fbf3  mov     [rsp+120h+var_F8], 2DCh
0x18000fbfb  call    McTemplateU0pqsq_EventWriteTransfer
0x18000fc00  jmp     loc_18000FAE6
0x18000fc05  mov     rcx, rbx; lpMem
0x18000fc08  call    KapiProcessUpdateRequest
0x18000fc0d  jmp     loc_18000FA00
0x18000fc12  mov     [rsp+120h+Reply], 8
0x18000fc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc21  lea     rax, WPP_GLOBAL_Control
0x18000fc28  cmp     rcx, rax
0x18000fc2b  jnz     loc_18000FCCC
0x18000fc31  mov     r14d, [rsp+120h+var_F0]
0x18000fc36  mov     esi, 1
0x18000fc3b  jmp     loc_18000F9D8
0x18000fc40  cmp     byte ptr [rcx+19h], 6
0x18000fc44  jb      loc_18000F97A
0x18000fc4a  mov     rcx, [rcx+10h]
0x18000fc4e  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000fc55  mov     edx, 32h ; '2'
0x18000fc5a  call    WPP_SF_
0x18000fc5f  jmp     loc_18000F97A
0x18000fc64  test    byte ptr [rcx+1Ch], 2
0x18000fc68  jz      loc_18000F9D5
0x18000fc6e  cmp     byte ptr [rcx+19h], 2
0x18000fc72  jb      loc_18000F9D5
0x18000fc78  mov     rcx, [rcx+10h]
0x18000fc7c  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000fc83  mov     edx, 33h ; '3'
0x18000fc88  mov     r9d, 490h
0x18000fc8e  call    WPP_SF_d
0x18000fc93  jmp     loc_18000F9D5
0x18000fc98  test    byte ptr [rcx+1Ch], 2
0x18000fc9c  jz      loc_18000FBDB
0x18000fca2  cmp     byte ptr [rcx+19h], 2
0x18000fca6  jb      loc_18000FBDB
0x18000fcac  mov     rcx, [rcx+10h]
0x18000fcb0  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000fcb7  mov     edx, 34h ; '4'
0x18000fcbc  mov     r9d, 57h ; 'W'
0x18000fcc2  call    WPP_SF_d
0x18000fcc7  jmp     loc_18000FBDB
0x18000fccc  test    byte ptr [rcx+1Ch], 2
0x18000fcd0  jz      loc_18000FC31
0x18000fcd6  cmp     byte ptr [rcx+19h], 2
0x18000fcda  jb      loc_18000FC31
0x18000fce0  mov     rcx, [rcx+10h]
0x18000fce4  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000fceb  mov     edx, 35h ; '5'
0x18000fcf0  mov     r9d, 8
0x18000fcf6  call    WPP_SF_d
0x18000fcfb  jmp     loc_18000FC31
0x18000fd00  mov     r9d, [rdi+10h]
0x18000fd04  lea     rdx, NcbKapiProviderReference
0x18000fd0b  mov     r8, rdi
0x18000fd0e  mov     [rsp+120h+var_F8], 2BDh
0x18000fd16  call    McTemplateU0pqsq_EventWriteTransfer
0x18000fd1b  jmp     loc_18000FBAF
0x18000fd20  lea     rdx, [rsp+120h+Reply]; Reply
0x18000fd25  mov     rcx, r15; pAsync
0x18000fd28  call    cs:__imp_RpcAsyncCompleteCall
0x18000fd2e  test    eax, eax
0x18000fd30  jz      loc_18000FA08
0x18000fd36  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd3d  lea     rbx, WPP_GLOBAL_Control
0x18000fd44  cmp     rcx, rbx
0x18000fd47  jz      loc_18000FA16
0x18000fd4d  test    byte ptr [rcx+1Ch], 2
0x18000fd51  jz      loc_18000FA16
0x18000fd57  cmp     byte ptr [rcx+19h], 2
0x18000fd5b  jb      loc_18000FA16
0x18000fd61  mov     rcx, [rcx+10h]
0x18000fd65  lea     r8, WPP_6aeccb702aab34019b2140bc812a3df3_Traceguids
0x18000fd6c  mov     edx, 36h ; '6'
0x18000fd71  mov     r9d, eax
0x18000fd74  call    WPP_SF_d
0x18000fd79  jmp     loc_18000FA0F
```
