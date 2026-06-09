# RpcOpenHandle

- ea: `0x180015950`
- end: `0x180015cc3`
- name: `RpcOpenHandle`
- size: `883`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800025f0`
- `0x180003114`
- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x180015950`

## import_xrefs

- `RPCRT4!RpcServerInqCallAttributesW` at `0x180015a34`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180015a34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a95`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015b5b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180015b5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015afc`

## pseudocode

```c
__int64 __fastcall RpcOpenHandle(__int64 a1, unsigned int a2, _DWORD *a3, struct _RTL_CRITICAL_SECTION **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  unsigned int v9; // r15d
  unsigned int v10; // ebx
  unsigned int v11; // eax
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  int v14; // ecx
  struct _RPC_CLIENT_INFO *i; // rax
  struct _RTL_CRITICAL_SECTION *v16; // rax
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION **v18; // rax
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-B8h] BYREF
  char v21[56]; // [rsp+48h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+80h] [rbp-78h]

  memset_0(RpcCallAttributes, 0, 0x70u);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 42, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, a2);
  }
  if ( !a4 )
    return 87;
  v8 = 0;
  v9 = 0;
  *a4 = 0;
  if ( g_bRpcServerStarted )
  {
    if ( a3 )
    {
      if ( a2 == 1 )
      {
        memset_0(v21, 0, 0x68u);
        RpcCallAttributes[0] = 2;
        RpcCallAttributes[1] = 16;
        v11 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
        v10 = v11;
        if ( v11 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_37;
          }
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 43, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v11);
        }
        else
        {
          v9 = v22;
          EnterCriticalSection(&stru_180052F50);
          if ( dword_180052EF8 == 128 )
            goto LABEL_17;
          v13 = 1;
          v14 = 0;
          for ( i = qword_180052EE8; i != (struct _RPC_CLIENT_INFO *)&qword_180052EE8; i = *(struct _RPC_CLIENT_INFO **)i )
          {
            if ( *((_DWORD *)i + 4) == v9 && (unsigned int)++v14 >= 0x14 )
            {
              v13 = 0;
              v8 = 0;
              break;
            }
            v8 = (struct _RTL_CRITICAL_SECTION *)i;
          }
          if ( !(_DWORD)v13 )
          {
LABEL_17:
            v10 = 1220;
          }
          else
          {
            v16 = (struct _RTL_CRITICAL_SECTION *)Dot3Alloc(0x878u, v13, (__int64)&qword_180052EE8);
            v8 = v16;
            if ( v16 )
            {
              memset_0(v16, 0, 0x878u);
              InitializeCriticalSection(v8 + 53);
              LODWORD(v8->OwningThread) = v9;
              HIDWORD(v8->OwningThread) = 1;
              LODWORD(v8[54].DebugInfo) = 1;
              v18 = (struct _RTL_CRITICAL_SECTION **)qword_180052EF0;
              if ( *(struct _RPC_CLIENT_INFO ***)qword_180052EF0 != &qword_180052EE8 )
                __fastfail(3u);
              v8->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&qword_180052EE8;
              *(_QWORD *)&v8->LockCount = v18;
              *v18 = v8;
              qword_180052EF0 = (__int64)v8;
              ++dword_180052EF8;
              *a3 = HIDWORD(v8->OwningThread);
              *a4 = v8;
            }
            else
            {
              LastError = GetLastError();
              v10 = LastError;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 44, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, LastError);
              }
            }
          }
          LeaveCriticalSection(&stru_180052F50);
        }
      }
      else
      {
        v10 = 1150;
      }
    }
    else
    {
      v10 = 87;
    }
  }
  else
  {
    v10 = 1722;
  }
  v12 = WPP_GLOBAL_Control;
LABEL_37:
  if ( v10 )
  {
    if ( v8 )
    {
      Dot3Free(v8);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v10 )
      goto LABEL_45;
  }
  if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(v12[1].Blink) >= 4u && (BYTE4(v12[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(v12[1].Flink, 46, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v9);
      v12 = WPP_GLOBAL_Control;
    }
LABEL_45:
    if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v12[1].Blink) >= 4u && (BYTE4(v12[1].Blink) & 1) != 0 )
      WPP_SF_d(v12[1].Flink, 47, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180015950  push    rbx
0x180015952  push    rsi
0x180015953  push    rdi
0x180015954  push    r12
0x180015956  push    r13
0x180015958  push    r14
0x18001595a  push    r15
0x18001595c  sub     rsp, 0C0h
0x180015963  mov     rax, cs:__security_cookie
0x18001596a  xor     rax, rsp
0x18001596d  mov     [rsp+0F8h+var_48], rax
0x180015975  mov     r12, r9
0x180015978  mov     rbx, r8
0x18001597b  mov     [rsp+0F8h+var_D0], rbx
0x180015980  mov     r13d, edx
0x180015983  xor     edx, edx; Val
0x180015985  lea     r8d, [rdx+70h]; Size
0x180015989  lea     rcx, [rsp+0F8h+RpcCallAttributes]; void *
0x18001598e  call    memset_0
0x180015993  lea     r14, WPP_GLOBAL_Control
0x18001599a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159a1  mov     edi, 1
0x1800159a6  cmp     rcx, r14
0x1800159a9  jz      short loc_1800159CD
0x1800159ab  cmp     byte ptr [rcx+19h], 4
0x1800159af  jb      short loc_1800159CD
0x1800159b1  test    [rcx+1Ch], dil
0x1800159b5  jz      short loc_1800159CD
0x1800159b7  lea     edx, [rdi+29h]
0x1800159ba  mov     r9d, r13d
0x1800159bd  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800159c4  mov     rcx, [rcx+10h]
0x1800159c8  call    WPP_SF_d
0x1800159cd  test    r12, r12
0x1800159d0  jnz     short loc_1800159DC
0x1800159d2  lea     eax, [r12+57h]
0x1800159d7  jmp     loc_180015CA0
0x1800159dc  xor     esi, esi
0x1800159de  xor     r15d, r15d
0x1800159e1  mov     [r12], rsi
0x1800159e5  cmp     cs:?g_bRpcServerStarted@@3EA, sil; uchar g_bRpcServerStarted
0x1800159ec  jnz     short loc_1800159F8
0x1800159ee  mov     ebx, 6BAh
0x1800159f3  jmp     loc_180015C22
0x1800159f8  test    rbx, rbx
0x1800159fb  jz      loc_180015C1D
0x180015a01  lea     eax, [r13-1]
0x180015a05  test    eax, eax
0x180015a07  jnz     loc_180015C16
0x180015a0d  xor     edx, edx; Val
0x180015a0f  lea     r8d, [rax+68h]; Size
0x180015a13  lea     rcx, [rsp+0F8h+var_B0]; void *
0x180015a18  call    memset_0
0x180015a1d  mov     [rsp+0F8h+RpcCallAttributes], 2
0x180015a25  mov     [rsp+0F8h+var_B4], 10h
0x180015a2d  lea     rdx, [rsp+0F8h+RpcCallAttributes]; RpcCallAttributes
0x180015a32  xor     ecx, ecx; ClientBinding
0x180015a34  call    cs:__imp_RpcServerInqCallAttributesW
0x180015a3a  mov     ebx, eax
0x180015a3c  test    eax, eax
0x180015a3e  jz      short loc_180015A81
0x180015a40  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a47  cmp     rcx, r14
0x180015a4a  jz      loc_180015C29
0x180015a50  cmp     [rcx+19h], dil
0x180015a54  jb      loc_180015C29
0x180015a5a  test    [rcx+1Ch], dil
0x180015a5e  jz      loc_180015C29
0x180015a64  mov     edx, 2Bh ; '+'
0x180015a69  mov     r9d, eax
0x180015a6c  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180015a73  mov     rcx, [rcx+10h]
0x180015a77  call    WPP_SF_d
0x180015a7c  jmp     loc_180015C22
0x180015a81  mov     r15d, [rsp+0F8h+var_78]
0x180015a89  mov     [rsp+0F8h+var_D8], r15d
0x180015a8e  lea     rcx, stru_180052F50; lpCriticalSection
0x180015a95  call    cs:__imp_EnterCriticalSection
0x180015a9b  cmp     cs:dword_180052EF8, 80h
0x180015aa5  jnz     short loc_180015AB1
0x180015aa7  mov     ebx, 4C4h
0x180015aac  jmp     loc_180015C07
0x180015ab1  mov     edx, edi
0x180015ab3  xor     ecx, ecx
0x180015ab5  mov     rax, cs:qword_180052EE8
0x180015abc  lea     r8, qword_180052EE8
0x180015ac3  cmp     rax, r8
0x180015ac6  jz      short loc_180015AE1
0x180015ac8  cmp     [rax+10h], r15d
0x180015acc  jnz     short loc_180015AD5
0x180015ace  inc     ecx
0x180015ad0  cmp     ecx, 14h
0x180015ad3  jnb     short loc_180015ADD
0x180015ad5  mov     rsi, rax
0x180015ad8  mov     rax, [rax]
0x180015adb  jmp     short loc_180015AC3
0x180015add  xor     edx, edx
0x180015adf  xor     esi, esi
0x180015ae1  test    edx, edx
0x180015ae3  jz      short loc_180015AA7
0x180015ae5  mov     ecx, 878h; dwBytes
0x180015aea  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x180015aef  mov     rsi, rax
0x180015af2  mov     [rsp+0F8h+var_C8], rax
0x180015af7  test    rax, rax
0x180015afa  jnz     short loc_180015B43
0x180015afc  call    cs:__imp_GetLastError
0x180015b02  mov     ebx, eax
0x180015b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b0b  cmp     rcx, r14
0x180015b0e  jz      loc_180015C07
0x180015b14  cmp     [rcx+19h], dil
0x180015b18  jb      loc_180015C07
0x180015b1e  test    [rcx+1Ch], dil
0x180015b22  jz      loc_180015C07
0x180015b28  lea     edx, [rsi+2Ch]
0x180015b2b  mov     r9d, eax
0x180015b2e  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180015b35  mov     rcx, [rcx+10h]
0x180015b39  call    WPP_SF_d
0x180015b3e  jmp     loc_180015C07
0x180015b43  xor     edx, edx; Val
0x180015b45  mov     r8d, 878h; Size
0x180015b4b  mov     rcx, rsi; void *
0x180015b4e  call    memset_0
0x180015b53  nop
0x180015b54  lea     rcx, [rsi+848h]; lpCriticalSection
0x180015b5b  call    cs:__imp_InitializeCriticalSection
0x180015b61  nop
0x180015b62  mov     [rsi+10h], r15d
0x180015b66  cmp     r13d, edi
0x180015b69  cmovnb  r13d, edi
0x180015b6d  mov     [rsi+14h], r13d
0x180015b71  mov     [rsi+870h], edi
0x180015b77  mov     rax, cs:qword_180052EF0
0x180015b7e  lea     rcx, qword_180052EE8
0x180015b85  cmp     [rax], rcx
0x180015b88  jz      short loc_180015B91
0x180015b8a  mov     ecx, 3
0x180015b8f  int     29h; Win8: RtlFailFast(ecx)
0x180015b91  mov     [rsi], rcx
0x180015b94  mov     [rsi+8], rax
0x180015b98  mov     [rax], rsi
0x180015b9b  mov     cs:qword_180052EF0, rsi
0x180015ba2  add     cs:dword_180052EF8, edi
0x180015ba8  mov     eax, [rsi+14h]
0x180015bab  mov     rcx, [rsp+0F8h+var_D0]
0x180015bb0  mov     [rcx], eax
0x180015bb2  mov     [r12], rsi
0x180015bb6  jmp     short loc_180015C07
0x180015bb8  mov     ebx, eax
0x180015bba  lea     rax, WPP_GLOBAL_Control
0x180015bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bc8  cmp     rcx, rax
0x180015bcb  jz      short loc_180015BF1
0x180015bcd  cmp     byte ptr [rcx+19h], 1
0x180015bd1  jb      short loc_180015BF1
0x180015bd3  test    byte ptr [rcx+1Ch], 1
0x180015bd7  jz      short loc_180015BF1
0x180015bd9  mov     edx, 2Dh ; '-'
0x180015bde  mov     r9d, ebx
0x180015be1  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180015be8  mov     rcx, [rcx+10h]
0x180015bec  call    WPP_SF_d
0x180015bf1  lea     r14, WPP_GLOBAL_Control
0x180015bf8  mov     edi, 1
0x180015bfd  mov     rsi, [rsp+0F8h+var_C8]
0x180015c02  mov     r15d, [rsp+0F8h+var_D8]
0x180015c07  lea     rcx, stru_180052F50; lpCriticalSection
0x180015c0e  call    cs:__imp_LeaveCriticalSection
0x180015c14  jmp     short loc_180015C22
0x180015c16  mov     ebx, 47Eh
0x180015c1b  jmp     short loc_180015C22
0x180015c1d  mov     ebx, 57h ; 'W'
0x180015c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c29  test    ebx, ebx
0x180015c2b  jz      short loc_180015C45
0x180015c2d  test    rsi, rsi
0x180015c30  jz      short loc_180015C41
0x180015c32  mov     rcx, rsi; lpMem
0x180015c35  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x180015c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c41  test    ebx, ebx
0x180015c43  jnz     short loc_180015C75
0x180015c45  cmp     rcx, r14
0x180015c48  jz      short loc_180015C9E
0x180015c4a  cmp     byte ptr [rcx+19h], 4
0x180015c4e  jb      short loc_180015C75
0x180015c50  test    [rcx+1Ch], dil
0x180015c54  jz      short loc_180015C75
0x180015c56  mov     edx, 2Eh ; '.'
0x180015c5b  mov     r9d, r15d
0x180015c5e  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180015c65  mov     rcx, [rcx+10h]
0x180015c69  call    WPP_SF_d
0x180015c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c75  cmp     rcx, r14
0x180015c78  jz      short loc_180015C9E
0x180015c7a  cmp     byte ptr [rcx+19h], 4
0x180015c7e  jb      short loc_180015C9E
0x180015c80  test    [rcx+1Ch], dil
0x180015c84  jz      short loc_180015C9E
0x180015c86  mov     edx, 2Fh ; '/'
0x180015c8b  mov     r9d, ebx
0x180015c8e  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180015c95  mov     rcx, [rcx+10h]
0x180015c99  call    WPP_SF_d
0x180015c9e  mov     eax, ebx
0x180015ca0  mov     rcx, [rsp+0F8h+var_48]
0x180015ca8  xor     rcx, rsp; StackCookie
0x180015cab  call    __security_check_cookie
0x180015cb0  add     rsp, 0C0h
0x180015cb7  pop     r15
0x180015cb9  pop     r14
0x180015cbb  pop     r13
0x180015cbd  pop     r12
0x180015cbf  pop     rdi
0x180015cc0  pop     rsi
0x180015cc1  pop     rbx
0x180015cc2  retn
```
