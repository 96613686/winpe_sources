# BthServRemoveAuthenticationClients(void *)

- ea: `0x180019ac0`
- end: `0x180019ce7`
- name: `?BthServRemoveAuthenticationClients@@YAXPEAX@Z`
- size: `551`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012f0c`

## callees

- `0x180011fd0`
- `0x180012004`
- `0x180012384`
- `0x180018ca0`
- `0x1800195fc`
- `0x180019ac0`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x180019c38`
- `ntdll!RtlRbRemoveNode` at `0x180019c38`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019b4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019b4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019c6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019c6f`

## pseudocode

```c
void __fastcall BthServRemoveAuthenticationClients(char *a1)
{
  char v2; // di
  bool v3; // dl
  _QWORD **v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rax
  _QWORD *v11; // r15
  int v12; // ebp
  struct _RTL_BALANCED_NODE *v13; // rax
  struct _RTL_BALANCED_NODE *v14; // rbx
  int v15; // eax

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( !WaitForSingleObject(hMutex, 0xFFFFFFFF) )
  {
    v4 = (_QWORD **)(a1 + 16);
    while ( 1 )
    {
      v5 = *v4;
      if ( *v4 == v4 )
        break;
      if ( (_QWORD **)v5[1] != v4
        || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5)
        || (*v4 = v6,
            v7 = v5 - 4,
            v6[1] = v4,
            v8 = (__int64)(v5 - 2),
            v9 = *(_QWORD *)v8,
            *(_QWORD *)(*(_QWORD *)v8 + 8LL) != v8)
        || (v10 = (_QWORD *)*(v5 - 1), *v10 != v8) )
      {
        __fastfail(3u);
      }
      *v10 = v9;
      *(_QWORD *)(v9 + 8) = v10;
      v11 = (_QWORD *)v7[1];
      if ( (_QWORD *)v11[5] == v11 + 5 )
      {
        v12 = qword_180047090 & 1;
        if ( (qword_180047090 & 1) == 0 )
        {
          v14 = qword_180047088;
          goto LABEL_28;
        }
        v13 = qword_180047088;
        if ( qword_180047088 )
        {
          v14 = (struct _RTL_BALANCED_NODE *)&qword_180047088;
LABEL_26:
          v14 = (struct _RTL_BALANCED_NODE *)((unsigned __int64)v13 ^ (unsigned __int64)v14);
LABEL_28:
          while ( v14 )
          {
            v15 = BthServAuthenticationClientCompare(v11, v14);
            if ( v15 >= 0 )
            {
              if ( v15 <= 0 )
                break;
              v13 = v14->Children[1];
            }
            else
            {
              v13 = v14->Children[0];
            }
            if ( v12 && v13 )
              goto LABEL_26;
            v14 = v13;
          }
          if ( v14 )
          {
            RtlRbRemoveNode(&qword_180047088, v14);
            SdpFreePool(v14);
          }
        }
      }
      BthServReleaseClientResources(v7);
      SdpFreePool(v7);
    }
    ReleaseMutex(hMutex);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
}

```

## disassembly

```asm
0x180019ac0  mov     [rsp+arg_0], rbx
0x180019ac5  mov     [rsp+arg_8], rbp
0x180019aca  mov     [rsp+arg_10], rsi
0x180019acf  push    rdi
0x180019ad0  push    r12
0x180019ad2  push    r13
0x180019ad4  push    r14
0x180019ad6  push    r15
0x180019ad8  sub     rsp, 50h
0x180019adc  mov     rbx, rcx
0x180019adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ae6  lea     r12, WPP_GLOBAL_Control
0x180019aed  mov     edi, 1
0x180019af2  cmp     rcx, r12
0x180019af5  jz      short loc_180019B02
0x180019af7  cmp     byte ptr [rcx+19h], 4
0x180019afb  jb      short loc_180019B02
0x180019afd  mov     dl, dil
0x180019b00  jmp     short loc_180019B04
0x180019b02  xor     dl, dl
0x180019b04  lea     r13, WPP_RECORDER_INITIALIZED
0x180019b0b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180019b12  lea     rbp, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180019b19  setnz   r8b
0x180019b1d  test    dl, dl
0x180019b1f  jnz     short loc_180019B26
0x180019b21  test    r8b, r8b
0x180019b24  jz      short loc_180019B44
0x180019b26  mov     r9, [rcx+28h]
0x180019b2a  mov     rcx, [rcx+10h]
0x180019b2e  mov     [rsp+78h+var_30], rbx
0x180019b33  mov     [rsp+78h+var_40], rbp
0x180019b38  mov     [rsp+78h+var_48], 19h
0x180019b3f  call    WPP_RECORDER_AND_TRACE_SF_si
0x180019b44  mov     rcx, cs:hMutex; hHandle
0x180019b4b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019b4e  call    cs:__imp_WaitForSingleObject
0x180019b55  nop     dword ptr [rax+rax+00h]
0x180019b5a  test    eax, eax
0x180019b5c  jnz     loc_180019CC8
0x180019b62  lea     rsi, [rbx+10h]
0x180019b66  mov     rax, [rsi]
0x180019b69  cmp     rax, rsi
0x180019b6c  jz      loc_180019C68
0x180019b72  cmp     [rax+8], rsi
0x180019b76  jnz     loc_180019C61
0x180019b7c  mov     rcx, [rax]
0x180019b7f  cmp     [rcx+8], rax
0x180019b83  jnz     loc_180019C61
0x180019b89  mov     [rsi], rcx
0x180019b8c  lea     r14, [rax-20h]
0x180019b90  mov     [rcx+8], rsi
0x180019b94  lea     rcx, [r14+10h]
0x180019b98  mov     rdx, [rcx]
0x180019b9b  cmp     [rdx+8], rcx
0x180019b9f  jnz     loc_180019C61
0x180019ba5  mov     rax, [rcx+8]
0x180019ba9  cmp     [rax], rcx
0x180019bac  jnz     loc_180019C61
0x180019bb2  mov     [rax], rdx
0x180019bb5  mov     [rdx+8], rax
0x180019bb9  mov     r15, [r14+8]
0x180019bbd  lea     rax, [r15+28h]
0x180019bc1  cmp     [rax], rax
0x180019bc4  jnz     loc_180019C4C
0x180019bca  mov     rax, cs:qword_180047090
0x180019bd1  movzx   ebp, al
0x180019bd4  and     ebp, edi
0x180019bd6  test    dil, al
0x180019bd9  jz      short loc_180019BF0
0x180019bdb  mov     rax, cs:qword_180047088
0x180019be2  test    rax, rax
0x180019be5  jz      short loc_180019C4C
0x180019be7  lea     rbx, qword_180047088
0x180019bee  jmp     short loc_180019C1C
0x180019bf0  mov     rbx, cs:qword_180047088
0x180019bf7  jmp     short loc_180019C24
0x180019bf9  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180019bfc  mov     rcx, r15; void *
0x180019bff  call    ?BthServAuthenticationClientCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; BthServAuthenticationClientCompare(void *,_RTL_BALANCED_NODE *)
0x180019c04  test    eax, eax
0x180019c06  jns     short loc_180019C0D
0x180019c08  mov     rax, [rbx]
0x180019c0b  jmp     short loc_180019C13
0x180019c0d  jle     short loc_180019C29
0x180019c0f  mov     rax, [rbx+8]
0x180019c13  test    ebp, ebp
0x180019c15  jz      short loc_180019C21
0x180019c17  test    rax, rax
0x180019c1a  jz      short loc_180019C21
0x180019c1c  xor     rbx, rax
0x180019c1f  jmp     short loc_180019C24
0x180019c21  mov     rbx, rax
0x180019c24  test    rbx, rbx
0x180019c27  jnz     short loc_180019BF9
0x180019c29  test    rbx, rbx
0x180019c2c  jz      short loc_180019C4C
0x180019c2e  mov     rdx, rbx
0x180019c31  lea     rcx, qword_180047088
0x180019c38  call    cs:__imp_RtlRbRemoveNode
0x180019c3f  nop     dword ptr [rax+rax+00h]
0x180019c44  mov     rcx, rbx
0x180019c47  call    SdpFreePool
0x180019c4c  mov     rcx, r14
0x180019c4f  call    BthServReleaseClientResources
0x180019c54  mov     rcx, r14
0x180019c57  call    SdpFreePool
0x180019c5c  jmp     loc_180019B66
0x180019c61  mov     ecx, 3
0x180019c66  int     29h; Win8: RtlFailFast(ecx)
0x180019c68  mov     rcx, cs:hMutex; hMutex
0x180019c6f  call    cs:__imp_ReleaseMutex
0x180019c76  nop     dword ptr [rax+rax+00h]
0x180019c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c82  cmp     rcx, r12
0x180019c85  jz      short loc_180019C8D
0x180019c87  cmp     byte ptr [rcx+19h], 4
0x180019c8b  jnb     short loc_180019C90
0x180019c8d  xor     dil, dil
0x180019c90  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180019c97  setnz   r8b
0x180019c9b  test    dil, dil
0x180019c9e  jnz     short loc_180019CA5
0x180019ca0  test    r8b, r8b
0x180019ca3  jz      short loc_180019CC8
0x180019ca5  mov     r9, [rcx+28h]
0x180019ca9  lea     rdx, WPP_8f95a5b1d9133c17f605a10539329b05_Traceguids
0x180019cb0  mov     rcx, [rcx+10h]
0x180019cb4  mov     [rsp+78h+var_40], rdx
0x180019cb9  mov     dl, dil
0x180019cbc  mov     [rsp+78h+var_48], 1Ah
0x180019cc3  call    WPP_RECORDER_AND_TRACE_SF_s
0x180019cc8  lea     r11, [rsp+78h+var_28]
0x180019ccd  mov     rbx, [r11+30h]
0x180019cd1  mov     rbp, [r11+38h]
0x180019cd5  mov     rsi, [r11+40h]
0x180019cd9  mov     rsp, r11
0x180019cdc  pop     r15
0x180019cde  pop     r14
0x180019ce0  pop     r13
0x180019ce2  pop     r12
0x180019ce4  pop     rdi
0x180019ce5  retn
```
