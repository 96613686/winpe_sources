# DafCreateAssociationSetContexts

- ea: `0x180008b40`
- end: `0x180008fb4`
- name: `DafCreateAssociationSetContexts`
- size: `1140`
- prototype: `__int64 __usercall@<rax>(struct _DAC_CLIENT_CONTEXT *@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180001dd8`
- `0x180001e1c`
- `0x180002284`
- `0x180002c50`
- `0x180002d4c`
- `0x180002dd0`
- `0x180002e88`
- `0x180002f10`
- `0x180008b40`
- `0x18000bbc2`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180008c7e`
- `RPCRT4!NdrClientCall3` at `0x180008c7e`

## pseudocode

```c
__int64 __fastcall DafCreateAssociationSetContexts(
        struct _DAC_CLIENT_CONTEXT *a1,
        int a2,
        int a3,
        __int64 a4,
        unsigned int *a5,
        void **a6,
        RPC_BINDING_HANDLE ***a7,
        _DWORD *a8)
{
  struct _DAC_CLIENT_CONTEXT *v10; // r13
  RPC_BINDING_HANDLE **v11; // r14
  _DWORD *v12; // r12
  CLIENT_CALL_RETURN v13; // rbx
  unsigned int Pointer; // eax
  RPC_BINDING_HANDLE **v15; // rax
  _DWORD *v16; // rax
  int v17; // r15d
  unsigned int v18; // ecx
  char *v19; // rdx
  __int64 v20; // rdi
  int Context; // eax
  int v22; // ecx
  size_t v23; // rbx
  void *v24; // rax
  void *v25; // rdi
  _QWORD *v26; // rax
  _QWORD *v27; // r15
  unsigned int v28; // r9d
  unsigned int v29; // ebx
  unsigned int i; // edi
  struct _DAC_CLIENT_CONTEXT *v31; // rcx
  unsigned int v32; // eax
  unsigned int v34; // [rsp+40h] [rbp-B8h] BYREF
  void *v35; // [rsp+48h] [rbp-B0h] BYREF
  CLIENT_CALL_RETURN v36; // [rsp+50h] [rbp-A8h]
  int v37; // [rsp+58h] [rbp-A0h] BYREF
  int v38[3]; // [rsp+5Ch] [rbp-9Ch] BYREF
  char *v39; // [rsp+68h] [rbp-90h]
  CLIENT_CALL_RETURN v40; // [rsp+70h] [rbp-88h]
  _DWORD v41[2]; // [rsp+80h] [rbp-78h] BYREF
  char *v42; // [rsp+88h] [rbp-70h]
  __int64 v43; // [rsp+90h] [rbp-68h]
  int v44; // [rsp+98h] [rbp-60h]
  int v45; // [rsp+9Ch] [rbp-5Ch]
  __int64 v46; // [rsp+A0h] [rbp-58h]
  __int64 v47; // [rsp+A8h] [rbp-50h]
  __int128 v48; // [rsp+B0h] [rbp-48h]
  unsigned int v50; // [rsp+100h] [rbp+8h]

  v10 = a1;
  v38[0] = 0;
  v34 = 0;
  v35 = 0;
  v37 = 0;
  v11 = 0;
  v12 = 0;
  v41[1] = 0;
  v47 = 0;
  v48 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids);
  if ( v10 && *((_WORD *)v10 + 4) == 3503 && (!a3 || a4) && a5 && a6 && a7 && a8 )
  {
    *a5 = 0;
    *a6 = 0;
    *a8 = 2;
    LODWORD(v13.Pointer) = PendCall(v10, v38);
    if ( !LODWORD(v13.Pointer) )
    {
      v36.Simple = 0;
      v13.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
                      8u,
                      0,
                      (char *)v10 + 56,
                      &v34,
                      &v35,
                      &v37).Pointer;
      v40.Pointer = v13.Pointer;
      v36.Pointer = v13.Pointer;
      v38[1] = (int)v13.Pointer;
      if ( !LODWORD(v13.Pointer) )
      {
        Pointer = v34;
        if ( v34 )
        {
          v15 = (RPC_BINDING_HANDLE **)DafMemAlloc(8LL * v34);
          v11 = v15;
          if ( !v15 )
            goto LABEL_16;
          memset_0(v15, 0, 8LL * v34);
          v16 = (_DWORD *)DafMemAlloc(4LL * v34);
          v12 = v16;
          if ( !v16 )
            goto LABEL_16;
          v17 = 0;
          memset_0(v16, 0, 4LL * v34);
          v18 = 0;
          LODWORD(v36.Pointer) = 0;
          Pointer = v34;
          if ( v34 )
          {
            v19 = (char *)v10 + 56;
            v39 = (char *)v10 + 56;
            do
            {
              v41[0] = 3;
              v45 = a3;
              v46 = a4;
              v44 = a2;
              v20 = v18;
              v43 = *((_QWORD *)v35 + v18);
              v42 = v19;
              Context = CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)v41, &v11[v18]);
              v12[v20] = Context;
              v22 = v17 + 1;
              if ( Context >= 0 )
                v22 = v17;
              v17 = v22;
              v18 = LODWORD(v36.Pointer) + 1;
              LODWORD(v36.Pointer) = v18;
              Pointer = v34;
              v19 = v39;
            }
            while ( v18 < v34 );
            LODWORD(v13.Pointer) = v40.Pointer;
            v10 = a1;
          }
          if ( v17 )
          {
            LODWORD(v36.Pointer) = Pointer - v17;
            if ( Pointer == v17 )
            {
              v25 = 0;
              v27 = 0;
            }
            else
            {
              v23 = 8LL * (Pointer - v17);
              v24 = (void *)DafMemAlloc(v23);
              v25 = v24;
              if ( !v24 )
              {
LABEL_16:
                LODWORD(v13.Pointer) = -2147024882;
                goto LABEL_39;
              }
              memset_0(v24, 0, v23);
              v26 = (_QWORD *)DafMemAlloc(v23);
              v27 = v26;
              if ( !v26 )
              {
                DafMemFree(v25);
                goto LABEL_16;
              }
              memset_0(v26, 0, v23);
              Pointer = v34;
            }
            v28 = 0;
            v50 = 0;
            v29 = 0;
            if ( Pointer )
            {
              do
              {
                if ( (int)v12[v29] < 0 )
                {
                  DafMemFree(*((void **)v35 + v29));
                  v28 = v50;
                }
                else
                {
                  v27[v28] = *((_QWORD *)v35 + v29);
                  *((_QWORD *)v25 + v28++) = v11[v29];
                  v50 = v28;
                }
                ++v29;
              }
              while ( v29 < v34 );
            }
            DafMemFree(v11);
            v11 = (RPC_BINDING_HANDLE **)v25;
            DafMemFree(v35);
            v35 = v27;
            Pointer = (unsigned int)v36.Pointer;
            LODWORD(v13.Pointer) = 6553601;
          }
        }
        *a5 = Pointer;
        v34 = 0;
        *a6 = v35;
        v35 = 0;
        *a7 = v11;
        v11 = 0;
        *a8 = v37;
      }
    }
  }
  else
  {
    LODWORD(v13.Pointer) = -2147024809;
  }
LABEL_39:
  if ( v35 )
    DafMemFree(v35);
  if ( v11 )
  {
    for ( i = 0; i < v34; ++i )
    {
      v31 = (struct _DAC_CLIENT_CONTEXT *)v11[i];
      if ( !v31 )
        break;
      v32 = CloseContext(v31);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids, v32);
    }
    DafMemFree(v11);
  }
  if ( v12 )
    DafMemFree(v12);
  if ( v38[0] )
    ClearPendingCall(v10);
  return LODWORD(v13.Pointer);
}

```

## disassembly

```asm
0x180008b40  mov     rax, rsp
0x180008b43  mov     [rax+20h], r9
0x180008b47  mov     [rax+18h], r8d
0x180008b4b  mov     [rax+10h], edx
0x180008b4e  mov     [rax+8], rcx
0x180008b52  push    rbx
0x180008b53  push    rsi
0x180008b54  push    rdi
0x180008b55  push    r12
0x180008b57  push    r13
0x180008b59  push    r14
0x180008b5b  push    r15
0x180008b5d  sub     rsp, 0C0h
0x180008b64  mov     rbx, r9
0x180008b67  mov     edi, r8d
0x180008b6a  mov     r13, rcx
0x180008b6d  xor     esi, esi
0x180008b6f  mov     [rsp+0F8h+var_9C], esi
0x180008b73  mov     [rsp+0F8h+var_B8], esi
0x180008b77  mov     [rsp+0F8h+var_B0], rsi
0x180008b7c  mov     [rsp+0F8h+var_A0], esi
0x180008b80  mov     r14d, esi
0x180008b83  mov     r12d, esi
0x180008b86  mov     [rax-74h], esi
0x180008b89  mov     [rax-50h], rsi
0x180008b8d  xorps   xmm0, xmm0
0x180008b90  movdqa  xmmword ptr [rax-48h], xmm0
0x180008b95  lea     r15, WPP_GLOBAL_Control
0x180008b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ba3  cmp     rcx, r15
0x180008ba6  jz      short loc_180008BC1
0x180008ba8  cmp     byte ptr [rcx+19h], 4
0x180008bac  jb      short loc_180008BC1
0x180008bae  lea     edx, [rsi+1Ah]
0x180008bb1  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x180008bb8  mov     rcx, [rcx+10h]
0x180008bbc  call    WPP_SF_s
0x180008bc1  test    r13, r13
0x180008bc4  jz      loc_180008F12
0x180008bca  mov     eax, 0DAFh
0x180008bcf  cmp     [r13+8], ax
0x180008bd4  jnz     loc_180008F12
0x180008bda  test    edi, edi
0x180008bdc  jz      short loc_180008BE7
0x180008bde  test    rbx, rbx
0x180008be1  jz      loc_180008F12
0x180008be7  mov     rax, [rsp+0F8h+arg_20]
0x180008bef  test    rax, rax
0x180008bf2  jz      loc_180008F12
0x180008bf8  mov     rcx, [rsp+0F8h+arg_28]
0x180008c00  test    rcx, rcx
0x180008c03  jz      loc_180008F12
0x180008c09  cmp     [rsp+0F8h+arg_30], rsi
0x180008c11  jz      loc_180008F12
0x180008c17  mov     rdx, [rsp+0F8h+arg_38]
0x180008c1f  test    rdx, rdx
0x180008c22  jz      loc_180008F12
0x180008c28  mov     [rax], esi
0x180008c2a  mov     [rcx], rsi
0x180008c2d  mov     dword ptr [rdx], 2
0x180008c33  lea     rdx, [rsp+0F8h+var_9C]; int *
0x180008c38  mov     rcx, r13; struct _DAC_CLIENT_CONTEXT *
0x180008c3b  call    ?PendCall@@YAJPEAU_DAC_CLIENT_CONTEXT@@PEAH@Z; PendCall(_DAC_CLIENT_CONTEXT *,int *)
0x180008c40  mov     ebx, eax
0x180008c42  test    eax, eax
0x180008c44  jnz     loc_180008F17
0x180008c4a  mov     [rsp+0F8h+var_A8], rsi
0x180008c4f  lea     r9, [r13+38h]
0x180008c53  lea     rax, [rsp+0F8h+var_A0]
0x180008c58  mov     [rsp+0F8h+var_C8], rax
0x180008c5d  lea     rax, [rsp+0F8h+var_B0]
0x180008c62  mov     [rsp+0F8h+var_D0], rax
0x180008c67  lea     rax, [rsp+0F8h+var_B8]
0x180008c6c  mov     [rsp+0F8h+var_D8], rax
0x180008c71  xor     r8d, r8d; pReturnValue
0x180008c74  lea     edx, [rbx+8]; nProcNum
0x180008c77  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180008c7e  call    cs:__imp_NdrClientCall3
0x180008c84  mov     rbx, rax
0x180008c87  mov     [rsp+0F8h+var_88], rax
0x180008c8c  mov     [rsp+0F8h+var_A8], rax
0x180008c91  mov     [rsp+0F8h+var_98], eax
0x180008c95  jmp     short loc_180008CBF
0x180008c97  cmp     eax, 1
0x180008c9a  jl      short loc_180008CA4
0x180008c9c  movzx   eax, ax
0x180008c9f  or      eax, 80010000h
0x180008ca4  mov     ebx, eax
0x180008ca6  mov     [rsp+0F8h+var_88], rbx
0x180008cab  mov     [rsp+0F8h+var_98], eax
0x180008caf  xor     esi, esi
0x180008cb1  mov     r13, [rsp+0F8h+arg_0]
0x180008cb9  mov     r14d, esi
0x180008cbc  mov     r12d, esi
0x180008cbf  test    ebx, ebx
0x180008cc1  jnz     loc_180008F17
0x180008cc7  mov     eax, [rsp+0F8h+var_B8]
0x180008ccb  test    eax, eax
0x180008ccd  jz      loc_180008ED1
0x180008cd3  mov     ecx, eax
0x180008cd5  shl     rcx, 3; size
0x180008cd9  call    DafMemAlloc
0x180008cde  mov     r14, rax
0x180008ce1  test    rax, rax
0x180008ce4  jnz     short loc_180008CF0
0x180008ce6  mov     ebx, 8007000Eh
0x180008ceb  jmp     loc_180008F17
0x180008cf0  mov     r8d, [rsp+0F8h+var_B8]
0x180008cf5  shl     r8, 3; Size
0x180008cf9  xor     edx, edx; Val
0x180008cfb  mov     rcx, r14; void *
0x180008cfe  call    memset_0
0x180008d03  mov     ecx, [rsp+0F8h+var_B8]
0x180008d07  shl     rcx, 2; size
0x180008d0b  call    DafMemAlloc
0x180008d10  mov     r12, rax
0x180008d13  test    rax, rax
0x180008d16  jz      short loc_180008CE6
0x180008d18  mov     r15d, esi
0x180008d1b  mov     r8d, [rsp+0F8h+var_B8]
0x180008d20  shl     r8, 2; Size
0x180008d24  xor     edx, edx; Val
0x180008d26  mov     rcx, rax; void *
0x180008d29  call    memset_0
0x180008d2e  mov     ecx, esi
0x180008d30  mov     dword ptr [rsp+0F8h+var_A8], ecx
0x180008d34  mov     eax, [rsp+0F8h+var_B8]
0x180008d38  test    eax, eax
0x180008d3a  jz      loc_180008DE1
0x180008d40  lea     rdx, [r13+38h]
0x180008d44  mov     [rsp+0F8h+var_90], rdx
0x180008d49  mov     r13, [rsp+0F8h+arg_18]
0x180008d51  mov     ebx, [rsp+0F8h+arg_10]
0x180008d58  mov     [rsp+0F8h+var_78], 3
0x180008d63  mov     [rsp+0F8h+var_5C], ebx
0x180008d6a  mov     [rsp+0F8h+var_58], r13
0x180008d72  mov     eax, [rsp+0F8h+arg_8]
0x180008d79  mov     [rsp+0F8h+var_60], eax
0x180008d80  mov     edi, ecx
0x180008d82  mov     rax, [rsp+0F8h+var_B0]
0x180008d87  mov     rcx, [rax+rdi*8]
0x180008d8b  mov     [rsp+0F8h+var_68], rcx
0x180008d93  mov     [rsp+0F8h+var_70], rdx
0x180008d9b  lea     rdx, [r14+rdi*8]; struct _DAC_CLIENT_CONTEXT **
0x180008d9f  lea     rcx, [rsp+0F8h+var_78]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x180008da7  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x180008dac  mov     [r12+rdi*4], eax
0x180008db0  lea     ecx, [r15+1]
0x180008db4  test    eax, eax
0x180008db6  cmovns  ecx, r15d
0x180008dba  mov     r15d, ecx
0x180008dbd  mov     ecx, dword ptr [rsp+0F8h+var_A8]
0x180008dc1  inc     ecx
0x180008dc3  mov     dword ptr [rsp+0F8h+var_A8], ecx
0x180008dc7  mov     eax, [rsp+0F8h+var_B8]
0x180008dcb  cmp     ecx, eax
0x180008dcd  mov     rdx, [rsp+0F8h+var_90]
0x180008dd2  jb      short loc_180008D58
0x180008dd4  mov     rbx, [rsp+0F8h+var_88]
0x180008dd9  mov     r13, [rsp+0F8h+arg_0]
0x180008de1  test    r15d, r15d
0x180008de4  jz      loc_180008ED1
0x180008dea  mov     ecx, eax
0x180008dec  sub     ecx, r15d
0x180008def  mov     dword ptr [rsp+0F8h+var_A8], ecx
0x180008df3  jz      short loc_180008E4C
0x180008df5  mov     ebx, ecx
0x180008df7  shl     rbx, 3
0x180008dfb  mov     rcx, rbx; size
0x180008dfe  call    DafMemAlloc
0x180008e03  mov     rdi, rax
0x180008e06  test    rax, rax
0x180008e09  jz      loc_180008CE6
0x180008e0f  mov     r8, rbx; Size
0x180008e12  xor     edx, edx; Val
0x180008e14  mov     rcx, rax; void *
0x180008e17  call    memset_0
0x180008e1c  mov     rcx, rbx; size
0x180008e1f  call    DafMemAlloc
0x180008e24  mov     r15, rax
0x180008e27  test    rax, rax
0x180008e2a  jnz     short loc_180008E39
0x180008e2c  mov     rcx, rdi; void *
0x180008e2f  call    DafMemFree
0x180008e34  jmp     loc_180008CE6
0x180008e39  mov     r8, rbx; Size
0x180008e3c  xor     edx, edx; Val
0x180008e3e  mov     rcx, rax; void *
0x180008e41  call    memset_0
0x180008e46  mov     eax, [rsp+0F8h+var_B8]
0x180008e4a  jmp     short loc_180008E52
0x180008e4c  mov     rdi, rsi
0x180008e4f  mov     r15, rsi
0x180008e52  mov     r9d, esi
0x180008e55  mov     dword ptr [rsp+0F8h+arg_0], esi
0x180008e5c  mov     ebx, esi
0x180008e5e  test    eax, eax
0x180008e60  jz      short loc_180008EAE
0x180008e62  mov     r8d, ebx
0x180008e65  cmp     [r12+r8*4], esi
0x180008e69  jl      short loc_180008E90
0x180008e6b  mov     edx, r9d
0x180008e6e  mov     rax, [rsp+0F8h+var_B0]
0x180008e73  mov     rcx, [rax+r8*8]
0x180008e77  mov     [r15+rdx*8], rcx
0x180008e7b  mov     rax, [r14+r8*8]
0x180008e7f  mov     [rdi+rdx*8], rax
0x180008e83  inc     r9d
0x180008e86  mov     dword ptr [rsp+0F8h+arg_0], r9d
0x180008e8e  jmp     short loc_180008EA6
0x180008e90  mov     rcx, [rsp+0F8h+var_B0]
0x180008e95  mov     rcx, [rcx+r8*8]; void *
0x180008e99  call    DafMemFree
0x180008e9e  mov     r9d, dword ptr [rsp+0F8h+arg_0]
0x180008ea6  inc     ebx
0x180008ea8  cmp     ebx, [rsp+0F8h+var_B8]
0x180008eac  jb      short loc_180008E62
0x180008eae  mov     rcx, r14; void *
0x180008eb1  call    DafMemFree
0x180008eb6  mov     r14, rdi
0x180008eb9  mov     rcx, [rsp+0F8h+var_B0]; void *
0x180008ebe  call    DafMemFree
0x180008ec3  mov     [rsp+0F8h+var_B0], r15
0x180008ec8  mov     eax, dword ptr [rsp+0F8h+var_A8]
0x180008ecc  mov     ebx, 640001h
0x180008ed1  mov     rcx, [rsp+0F8h+arg_20]
0x180008ed9  mov     [rcx], eax
0x180008edb  mov     [rsp+0F8h+var_B8], esi
0x180008edf  mov     rax, [rsp+0F8h+var_B0]
0x180008ee4  mov     rcx, [rsp+0F8h+arg_28]
0x180008eec  mov     [rcx], rax
0x180008eef  mov     [rsp+0F8h+var_B0], rsi
0x180008ef4  mov     rax, [rsp+0F8h+arg_30]
0x180008efc  mov     [rax], r14
0x180008eff  mov     r14, rsi
0x180008f02  mov     eax, [rsp+0F8h+var_A0]
0x180008f06  mov     rcx, [rsp+0F8h+arg_38]
0x180008f0e  mov     [rcx], eax
0x180008f10  jmp     short loc_180008F17
0x180008f12  mov     ebx, 80070057h
0x180008f17  mov     rcx, [rsp+0F8h+var_B0]; void *
0x180008f1c  test    rcx, rcx
0x180008f1f  jz      short loc_180008F26
0x180008f21  call    DafMemFree
0x180008f26  test    r14, r14
0x180008f29  jz      short loc_180008F84
0x180008f2b  mov     edi, esi
0x180008f2d  cmp     [rsp+0F8h+var_B8], esi
0x180008f31  jbe     short loc_180008F7C
0x180008f33  lea     r15, WPP_GLOBAL_Control
0x180008f3a  mov     eax, edi
0x180008f3c  mov     rcx, [r14+rax*8]; struct _DAC_CLIENT_CONTEXT *
0x180008f40  test    rcx, rcx
0x180008f43  jz      short loc_180008F7C
0x180008f45  call    ?CloseContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@@Z; CloseContext(_DAC_CLIENT_CONTEXT *)
0x180008f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f51  cmp     rcx, r15
0x180008f54  jz      short loc_180008F74
0x180008f56  cmp     byte ptr [rcx+19h], 2
0x180008f5a  jb      short loc_180008F74
0x180008f5c  mov     edx, 1Bh
0x180008f61  mov     r9d, eax
0x180008f64  lea     r8, WPP_09b1b66130ac391e30ae78ef35ffcad1_Traceguids
0x180008f6b  mov     rcx, [rcx+10h]
0x180008f6f  call    WPP_SF_D
0x180008f74  inc     edi
0x180008f76  cmp     edi, [rsp+0F8h+var_B8]
0x180008f7a  jb      short loc_180008F3A
0x180008f7c  mov     rcx, r14; void *
0x180008f7f  call    DafMemFree
0x180008f84  test    r12, r12
0x180008f87  jz      short loc_180008F91
0x180008f89  mov     rcx, r12; void *
0x180008f8c  call    DafMemFree
0x180008f91  cmp     [rsp+0F8h+var_9C], esi
0x180008f95  jz      short loc_180008F9F
0x180008f97  mov     rcx, r13; struct _DAC_CLIENT_CONTEXT *
0x180008f9a  call    ?ClearPendingCall@@YAXPEAU_DAC_CLIENT_CONTEXT@@@Z; ClearPendingCall(_DAC_CLIENT_CONTEXT *)
0x180008f9f  mov     eax, ebx
0x180008fa1  add     rsp, 0C0h
0x180008fa8  pop     r15
0x180008faa  pop     r14
0x180008fac  pop     r13
0x180008fae  pop     r12
0x180008fb0  pop     rdi
0x180008fb1  pop     rsi
0x180008fb2  pop     rbx
0x180008fb3  retn
0x18000c036  push    rbp
0x18000c038  sub     rsp, 40h
0x18000c03c  mov     rbp, rdx
0x18000c03f  mov     rcx, [rcx]
0x18000c042  mov     ecx, [rcx]; ExceptionCode
0x18000c044  call    cs:__imp_I_RpcExceptionFilter
0x18000c04a  nop
0x18000c04b  add     rsp, 40h
0x18000c04f  pop     rbp
0x18000c050  retn
```
