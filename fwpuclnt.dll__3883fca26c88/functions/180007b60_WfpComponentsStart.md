# WfpComponentsStart

- ea: `0x180007b60`
- end: `0x180007c72`
- name: `WfpComponentsStart`
- size: `274`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800072e0`
- `0x180007380`
- `0x180013bb4`

## callees

- `0x180007b60`
- `0x180007e38`
- `0x180007ec0`
- `0x18000e6ac`
- `0x18000f624`
- `0x18003b5c8`
- `0x18004b010`

## string_xrefs

- `0x180007baa`: `WfpComponentDispatch`
- `0x180007bb9`: `WfpComponentsDispatchForward`
- `0x180007bd3`: `WfpComponentsStart`

## pseudocode

```c
__int64 __fastcall WfpComponentsStart(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  _BYTE *v4; // r10
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 ControlName; // rax
  __int64 v11; // r10
  int v12; // r8d

  v1 = 0;
  v2 = 0;
  if ( a1[1] )
  {
    v4 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      v5 = *a1;
      if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 3u && (v4[28] & 1) != 0 )
      {
        ControlName = WfpComponentGetControlName(0);
        WPP_SF_SSS(*(_QWORD *)(v11 + 16), ControlName, v12, 0, ControlName, *(_QWORD *)(v5 + 16 * v2 + 8));
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v5 + 16 * v2))(0, 0);
      v1 = v6;
      if ( v6 )
        break;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids, 0);
        v4 = WPP_GLOBAL_Control;
      }
      if ( ++v2 >= (unsigned __int64)a1[1] )
        return v1;
    }
    WfpReportError(v6, "WfpComponentDispatch");
    WfpReportError(v1, "WfpComponentsDispatchForward");
    WfpComponentsDispatchReverse(a1, v7, v8, v2);
    WfpReportError(v1, "WfpComponentsStart");
  }
  return v1;
}

```

## disassembly

```asm
0x180007b60  push    rbx
0x180007b62  push    rbp
0x180007b63  push    rsi
0x180007b64  push    rdi
0x180007b65  push    r14
0x180007b67  sub     rsp, 30h
0x180007b6b  xor     ebx, ebx
0x180007b6d  xor     edi, edi
0x180007b6f  mov     rsi, rcx
0x180007b72  cmp     [rcx+8], rbx
0x180007b76  jbe     short loc_180007BE2
0x180007b78  mov     r10, cs:WPP_GLOBAL_Control
0x180007b7f  lea     r14, WPP_GLOBAL_Control
0x180007b86  mov     rbp, [rsi]
0x180007b89  mov     rbx, rdi
0x180007b8c  add     rbx, rbx
0x180007b8f  cmp     r10, r14
0x180007b92  jnz     short loc_180007BF1
0x180007b94  mov     rax, [rbp+rbx*8+0]
0x180007b99  xor     edx, edx
0x180007b9b  xor     ecx, ecx
0x180007b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba2  mov     rbx, rax
0x180007ba5  test    rax, rax
0x180007ba8  jz      short loc_180007C29
0x180007baa  lea     rdx, aWfpcomponentdi; "WfpComponentDispatch"
0x180007bb1  mov     rcx, rax
0x180007bb4  call    WfpReportError
0x180007bb9  lea     rdx, aWfpcomponentsd; "WfpComponentsDispatchForward"
0x180007bc0  mov     rcx, rbx
0x180007bc3  call    WfpReportError
0x180007bc8  mov     r9, rdi
0x180007bcb  mov     rcx, rsi
0x180007bce  call    WfpComponentsDispatchReverse
0x180007bd3  lea     rdx, aWfpcomponentss; "WfpComponentsStart"
0x180007bda  mov     rcx, rbx
0x180007bdd  call    WfpReportError
0x180007be2  mov     rax, rbx
0x180007be5  add     rsp, 30h
0x180007be9  pop     r14
0x180007beb  pop     rdi
0x180007bec  pop     rsi
0x180007bed  pop     rbp
0x180007bee  pop     rbx
0x180007bef  retn
0x180007bf1  cmp     byte ptr [r10+19h], 3
0x180007bf6  jb      short loc_180007B94
0x180007bf8  test    byte ptr [r10+1Ch], 1
0x180007bfd  jz      short loc_180007B94
0x180007bff  xor     ecx, ecx
0x180007c01  call    WfpComponentGetControlName
0x180007c06  mov     rcx, [r10+10h]
0x180007c0a  mov     rdx, rax
0x180007c0d  mov     rax, [rbp+rbx*8+8]
0x180007c12  xor     r9d, r9d
0x180007c15  mov     [rsp+58h+var_30], rax
0x180007c1a  mov     [rsp+58h+var_38], rdx
0x180007c1f  call    WPP_SF_SSS
0x180007c24  jmp     loc_180007B94
0x180007c29  mov     r10, cs:WPP_GLOBAL_Control
0x180007c30  cmp     r10, r14
0x180007c33  jz      short loc_180007C3C
0x180007c35  cmp     byte ptr [r10+19h], 3
0x180007c3a  jnb     short loc_180007C4A
0x180007c3c  inc     rdi
0x180007c3f  cmp     rdi, [rsi+8]
0x180007c43  jnb     short loc_180007BE2
0x180007c45  jmp     loc_180007B86
0x180007c4a  test    byte ptr [r10+1Ch], 1
0x180007c4f  jz      short loc_180007C3C
0x180007c51  mov     rcx, [r10+10h]
0x180007c55  lea     r8, WPP_afd810515d1c3db64468bc5743bd872b_Traceguids
0x180007c5c  mov     edx, 0Bh
0x180007c61  xor     r9d, r9d
0x180007c64  call    WPP_SF_S
0x180007c69  mov     r10, cs:WPP_GLOBAL_Control
0x180007c70  jmp     short loc_180007C3C
```
