# DwmRenderGesture

- ea: `0x18000a8e0`
- end: `0x18000aa7e`
- name: `DwmRenderGesture`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000352c`
- `0x180005b5c`
- `0x18000925c`
- `0x18000a8e0`
- `0x18000d0a0`
- `0x180013a20`

## import_xrefs

- `USER32!__imp_TransformPoint` at `0x18000a9d4`
- `USER32!__imp_TransformPoint` at `0x18000a9e4`
- `USER32!__imp_TransformPoint` at `0x18000a9d4`
- `USER32!__imp_TransformPoint` at `0x18000a9e4`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18000a9bd`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18000a9bd`

## pseudocode

```c
__int64 __fastcall DwmRenderGesture(unsigned int a1, int a2, int *a3, _QWORD *a4)
{
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 ThreadDpiAwarenessContext; // rbx
  CApiPortClient *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  unsigned int v18; // [rsp+20h] [rbp-40h]
  void *v19; // [rsp+28h] [rbp-38h]
  void *v20; // [rsp+28h] [rbp-38h]
  int v21; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v22[4]; // [rsp+38h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiRenderGesture_Start);
  if ( !a3 || !a4 || (unsigned int)(a2 - 1) > 1 )
  {
    v18 = 72;
    goto LABEL_19;
  }
  if ( a2 == 2 )
  {
    if ( a1 != 10 )
    {
      v18 = 80;
LABEL_19:
      v16 = -2147024809;
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019650, 1u, -2147024809, v18, v19);
      goto LABEL_20;
    }
  }
  else if ( a1 == 10 )
  {
    v18 = 87;
    goto LABEL_19;
  }
  v8 = *a3;
  memset((char *)v22 + 4, 0, 28);
  LODWORD(v22[1]) = v8;
  *(_QWORD *)((char *)&v22[1] + 4) = *a4;
  v9 = 0;
  LODWORD(v22[0]) = 1073741889;
  HIDWORD(v22[0]) = a1;
  if ( a2 == 2 )
    v9 = 1;
  HIDWORD(v22[2]) = a3[v9];
  v10 = 0;
  if ( a2 == 2 )
    v10 = 1;
  v22[3] = a4[v10];
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  TransformPoint((char *)&v22[1] + 4, -3, ThreadDpiAwarenessContext);
  TransformPoint(&v22[3], -3, ThreadDpiAwarenessContext);
  v21 = 0;
  v13 = CApiPortClient::SendRequest(v12, v22, 32, &v21, 0, 0);
  v16 = v13;
  if ( v13 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019650, 1u, v13, 0x6Bu, v20);
  else
    v16 = v21;
LABEL_20:
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(v15, v14, v16, a1);
  return v16;
}

```

## disassembly

```asm
0x18000a8e0  push    rbp
0x18000a8e2  push    rbx
0x18000a8e3  push    rsi
0x18000a8e4  push    rdi
0x18000a8e5  push    r12
0x18000a8e7  push    r14
0x18000a8e9  push    r15
0x18000a8eb  mov     rbp, rsp
0x18000a8ee  sub     rsp, 60h
0x18000a8f2  mov     rax, cs:__security_cookie
0x18000a8f9  xor     rax, rsp
0x18000a8fc  mov     [rbp+var_8], rax
0x18000a900  mov     r12d, 1
0x18000a906  mov     r15, r9
0x18000a909  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, r12b
0x18000a910  mov     r14, r8
0x18000a913  mov     ebx, edx
0x18000a915  mov     esi, ecx
0x18000a917  jz      short loc_18000A92F
0x18000a919  mov     r8d, ecx
0x18000a91c  lea     rdx, ApiRenderGesture_Start
0x18000a923  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000a92a  call    McTemplateU0q_EtwEventWriteTransfer
0x18000a92f  test    r14, r14
0x18000a932  jz      loc_18000AA28
0x18000a938  test    r15, r15
0x18000a93b  jz      loc_18000AA28
0x18000a941  lea     eax, [rbx-1]
0x18000a944  cmp     eax, r12d
0x18000a947  ja      loc_18000AA28
0x18000a94d  cmp     ebx, 2
0x18000a950  jnz     short loc_18000A964
0x18000a952  cmp     esi, 0Ah
0x18000a955  jz      short loc_18000A976
0x18000a957  mov     dword ptr [rsp+60h+var_40], 50h ; 'P'
0x18000a95f  jmp     loc_18000AA30
0x18000a964  cmp     esi, 0Ah
0x18000a967  jnz     short loc_18000A976
0x18000a969  mov     dword ptr [rsp+60h+var_40], 57h ; 'W'
0x18000a971  jmp     loc_18000AA30
0x18000a976  mov     eax, [r14]
0x18000a979  xorps   xmm0, xmm0
0x18000a97c  movups  [rbp+var_24], xmm0
0x18000a980  mov     dword ptr [rbp+var_24+4], eax
0x18000a983  mov     rax, [r15]
0x18000a986  movups  [rbp+var_24+0Ch], xmm0
0x18000a98a  mov     qword ptr [rbp+var_24+8], rax
0x18000a98e  xor     eax, eax
0x18000a990  cmp     ebx, 2
0x18000a993  mov     [rbp+var_28], 40000041h
0x18000a99a  mov     dword ptr [rbp+var_24], esi
0x18000a99d  lea     edi, [rax+4]
0x18000a9a0  cmovz   eax, edi
0x18000a9a3  lea     ecx, [rdi+4]
0x18000a9a6  mov     eax, [rax+r14]
0x18000a9aa  mov     [rbp+var_14], eax
0x18000a9ad  xor     eax, eax
0x18000a9af  cmp     ebx, 2
0x18000a9b2  cmovz   eax, ecx
0x18000a9b5  mov     rax, [rax+r15]
0x18000a9b9  mov     [rbp+var_10], rax
0x18000a9bd  call    cs:__imp_GetThreadDpiAwarenessContext
0x18000a9c3  lea     r14, [rdi-7]
0x18000a9c7  mov     r8, rax
0x18000a9ca  mov     rdx, r14
0x18000a9cd  lea     rcx, [rbp+var_24+8]
0x18000a9d1  mov     rbx, rax
0x18000a9d4  call    cs:__imp_TransformPoint
0x18000a9da  mov     r8, rbx
0x18000a9dd  lea     rcx, [rbp+var_10]
0x18000a9e1  mov     rdx, r14
0x18000a9e4  call    cs:__imp_TransformPoint
0x18000a9ea  xor     eax, eax
0x18000a9ec  mov     [rbp+var_30], 0
0x18000a9f3  mov     word ptr [rsp+60h+var_38], ax; __int16
0x18000a9f8  lea     r8d, [rdi+1Ch]; __int16
0x18000a9fc  lea     r9, [rbp+var_30]; int *
0x18000aa00  mov     [rsp+60h+var_40], rax; void *
0x18000aa05  lea     rdx, [rbp+var_28]; void *
0x18000aa09  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x18000aa0e  mov     ebx, eax
0x18000aa10  test    eax, eax
0x18000aa12  js      short loc_18000AA19
0x18000aa14  mov     ebx, [rbp+var_30]
0x18000aa17  jmp     short loc_18000AA4D
0x18000aa19  mov     dword ptr [rsp+60h+var_40], 6Bh ; 'k'
0x18000aa21  mov     r9d, eax
0x18000aa24  mov     ecx, edi
0x18000aa26  jmp     short loc_18000AA3E
0x18000aa28  mov     dword ptr [rsp+60h+var_40], 48h ; 'H'; unsigned int
0x18000aa30  mov     r9d, 80070057h; int
0x18000aa36  mov     ecx, 4; unsigned int
0x18000aa3b  mov     ebx, r9d
0x18000aa3e  mov     r8d, r12d; unsigned int
0x18000aa41  lea     rdx, qword_180019650; int *
0x18000aa48  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000aa4d  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, r12b
0x18000aa54  jz      short loc_18000AA61
0x18000aa56  mov     r9d, esi
0x18000aa59  mov     r8d, ebx
0x18000aa5c  call    McTemplateU0qq_EtwEventWriteTransfer
0x18000aa61  mov     eax, ebx
0x18000aa63  mov     rcx, [rbp+var_8]
0x18000aa67  xor     rcx, rsp; StackCookie
0x18000aa6a  call    __security_check_cookie
0x18000aa6f  add     rsp, 60h
0x18000aa73  pop     r15
0x18000aa75  pop     r14
0x18000aa77  pop     r12
0x18000aa79  pop     rdi
0x18000aa7a  pop     rsi
0x18000aa7b  pop     rbx
0x18000aa7c  pop     rbp
0x18000aa7d  retn
```
