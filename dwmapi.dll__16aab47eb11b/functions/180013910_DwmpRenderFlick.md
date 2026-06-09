# DwmpRenderFlick

- ea: `0x180013910`
- end: `0x180013a17`
- name: `DwmpRenderFlick`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000352c`
- `0x180004594`
- `0x180005b5c`
- `0x18000925c`
- `0x18000d0a0`
- `0x180013910`

## import_xrefs

- `USER32!__imp_TransformPoint` at `0x18001397f`
- `USER32!__imp_TransformPoint` at `0x18001397f`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001396a`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001396a`

## pseudocode

```c
__int64 __fastcall DwmpRenderFlick(__int32 a1, __int64 a2, __int64 a3)
{
  __int64 ThreadDpiAwarenessContext; // rax
  CApiPortClient *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  void *v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+40h] [rbp-28h] BYREF

  v11 = a2;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApipRenderFlick_Start,
      a3,
      1,
      (__int64)&si128);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  si128.m128i_i32[1] = a1;
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  TransformPoint(&v11, -3, ThreadDpiAwarenessContext);
  si128.m128i_i64[1] = v11;
  v10 = 0;
  v6 = CApiPortClient::SendRequest(v5, &si128, 16, &v10, 0, 0);
  v7 = v6;
  if ( v6 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A120, 1u, v6, 0x27u, v9);
  else
    v7 = v10;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApipRenderFlick_Stop);
  return v7;
}

```

## disassembly

```asm
0x180013910  push    rbx
0x180013912  sub     rsp, 60h
0x180013916  mov     rax, cs:__security_cookie
0x18001391d  xor     rax, rsp
0x180013920  mov     [rsp+68h+var_18], rax
0x180013925  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18001392c  mov     ebx, ecx
0x18001392e  mov     [rsp+68h+var_30], rdx
0x180013933  jz      short loc_180013958
0x180013935  lea     rax, [rsp+68h+var_28]
0x18001393a  mov     r9d, 1
0x180013940  lea     rdx, ApipRenderFlick_Start
0x180013947  mov     [rsp+68h+var_48], rax
0x18001394c  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180013953  call    McGenEventWrite_EtwEventWriteTransfer
0x180013958  movdqa  xmm0, cs:__xmm@00000000000000000000000040000042
0x180013960  movdqu  [rsp+68h+var_28], xmm0
0x180013966  mov     dword ptr [rsp+68h+var_28+4], ebx
0x18001396a  call    cs:__imp_GetThreadDpiAwarenessContext
0x180013970  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x180013977  lea     rcx, [rsp+68h+var_30]
0x18001397c  mov     r8, rax
0x18001397f  call    cs:__imp_TransformPoint
0x180013985  mov     rax, [rsp+68h+var_30]
0x18001398a  lea     r9, [rsp+68h+var_38]; int *
0x18001398f  mov     qword ptr [rsp+68h+var_28+8], rax
0x180013994  lea     rdx, [rsp+68h+var_28]; void *
0x180013999  xor     eax, eax
0x18001399b  mov     [rsp+68h+var_38], 0
0x1800139a3  mov     word ptr [rsp+68h+var_40], ax; void *
0x1800139a8  mov     [rsp+68h+var_48], rax; void *
0x1800139ad  lea     r8d, [rax+10h]; __int16
0x1800139b1  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x1800139b6  mov     ebx, eax
0x1800139b8  test    eax, eax
0x1800139ba  js      short loc_1800139C2
0x1800139bc  mov     ebx, [rsp+68h+var_38]
0x1800139c0  jmp     short loc_1800139E3
0x1800139c2  mov     r8d, 1; unsigned int
0x1800139c8  mov     dword ptr [rsp+68h+var_48], 27h ; '''; unsigned int
0x1800139d0  mov     r9d, eax; int
0x1800139d3  lea     rdx, qword_18001A120; int *
0x1800139da  lea     ecx, [r8+3]; unsigned int
0x1800139de  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800139e3  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x1800139ea  jz      short loc_180013A02
0x1800139ec  mov     r8d, ebx
0x1800139ef  lea     rdx, ApipRenderFlick_Stop
0x1800139f6  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x1800139fd  call    McTemplateU0q_EtwEventWriteTransfer
0x180013a02  mov     eax, ebx
0x180013a04  mov     rcx, [rsp+68h+var_18]
0x180013a09  xor     rcx, rsp; StackCookie
0x180013a0c  call    __security_check_cookie
0x180013a11  add     rsp, 60h
0x180013a15  pop     rbx
0x180013a16  retn
```
