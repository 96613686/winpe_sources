# CleanupAsyncUserContext(_DAC_CLIENT_CONTEXT *,int,_DAC_ASYNC_USER_CONTEXT * *)

- ea: `0x180001d38`
- end: `0x180001dcf`
- name: `?CleanupAsyncUserContext@@YAXPEAU_DAC_CLIENT_CONTEXT@@HPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z`
- size: `151`
- prototype: `void __fastcall(struct _DAC_CLIENT_CONTEXT *, int, struct _DAC_ASYNC_USER_CONTEXT **)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1800090b0`
- `0x1800091e0`
- `0x180009320`
- `0x180009450`
- `0x180009580`
- `0x1800096a0`
- `0x180009890`
- `0x180009fa4`
- `0x18000a4b0`
- `0x18000a5e0`

## callees

- `0x180001d38`
- `0x180001dd8`
- `0x180002a54`
- `0x180002ca4`
- `0x180002f10`

## pseudocode

```c
void __fastcall CleanupAsyncUserContext(struct _DAC_CLIENT_CONTEXT *a1, int a2, struct _DAC_ASYNC_USER_CONTEXT **a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Eu, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
  ReleaseClientContext(a1);
  if ( a2 )
    ClearPendingCall(a1);
  if ( *a3 )
  {
    FreeAsyncUserContext(*a3);
    *a3 = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Fu, &WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids);
}

```

## disassembly

```asm
0x180001d38  push    rbx
0x180001d3a  push    rbp
0x180001d3b  push    rsi
0x180001d3c  push    rdi
0x180001d3d  sub     rsp, 28h
0x180001d41  mov     rbx, r8
0x180001d44  mov     esi, edx
0x180001d46  mov     rdi, rcx
0x180001d49  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d50  lea     rbp, WPP_GLOBAL_Control
0x180001d57  cmp     rcx, rbp
0x180001d5a  jz      short loc_180001D77
0x180001d5c  cmp     byte ptr [rcx+19h], 4
0x180001d60  jb      short loc_180001D77
0x180001d62  mov     rcx, [rcx+10h]
0x180001d66  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180001d6d  mov     edx, 1Eh
0x180001d72  call    WPP_SF_s
0x180001d77  mov     rcx, rdi; struct _DAC_CLIENT_CONTEXT *
0x180001d7a  call    ?ReleaseClientContext@@YAKPEAU_DAC_CLIENT_CONTEXT@@@Z; ReleaseClientContext(_DAC_CLIENT_CONTEXT *)
0x180001d7f  test    esi, esi
0x180001d81  jz      short loc_180001D8B
0x180001d83  mov     rcx, rdi; struct _DAC_CLIENT_CONTEXT *
0x180001d86  call    ?ClearPendingCall@@YAXPEAU_DAC_CLIENT_CONTEXT@@@Z; ClearPendingCall(_DAC_CLIENT_CONTEXT *)
0x180001d8b  mov     rcx, [rbx]; struct _DAC_ASYNC_USER_CONTEXT *
0x180001d8e  test    rcx, rcx
0x180001d91  jz      short loc_180001D9F
0x180001d93  call    ?FreeAsyncUserContext@@YAXPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; FreeAsyncUserContext(_DAC_ASYNC_USER_CONTEXT *)
0x180001d98  mov     qword ptr [rbx], 0
0x180001d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001da6  cmp     rcx, rbp
0x180001da9  jz      short loc_180001DC6
0x180001dab  cmp     byte ptr [rcx+19h], 4
0x180001daf  jb      short loc_180001DC6
0x180001db1  mov     rcx, [rcx+10h]
0x180001db5  lea     r8, WPP_bf3c54b8c13833bf7cdfafd9cf29bac0_Traceguids
0x180001dbc  mov     edx, 1Fh
0x180001dc1  call    WPP_SF_s
0x180001dc6  add     rsp, 28h
0x180001dca  pop     rdi
0x180001dcb  pop     rsi
0x180001dcc  pop     rbp
0x180001dcd  pop     rbx
0x180001dce  retn
```
