# DwmTetherContact

- ea: `0x180013800`
- end: `0x1800138fd`
- name: `DwmTetherContact`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000352c`
- `0x180004594`
- `0x180005b5c`
- `0x18000ade0`
- `0x18000d0a0`
- `0x180013800`

## import_xrefs

- `USER32!__imp_TransformPoint` at `0x18001387a`
- `USER32!__imp_TransformPoint` at `0x18001387a`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x180013865`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x180013865`

## pseudocode

```c
__int64 __fastcall DwmTetherContact(int a1, int a2, __int64 a3)
{
  __int64 ThreadDpiAwarenessContext; // rax
  CApiPortClient *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  void *v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  _DWORD v12[3]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v13; // [rsp+44h] [rbp-24h]

  v11 = a3;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApiTetherContact_Start,
      a3,
      1,
      (__int64)v12);
  v12[0] = 1073741892;
  v13 = 0;
  v12[1] = a1;
  v12[2] = a2;
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  TransformPoint(&v11, -3, ThreadDpiAwarenessContext);
  v13 = v11;
  v7 = CApiPortClient::SendNotification(v6, v12, 20);
  v8 = v7;
  if ( v7 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(4u, &byte_18001A118, 1u, v7, 0xB1u, v10);
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiTetherContact_Stop);
  return v8;
}

```

## disassembly

```asm
0x180013800  mov     r11, rsp
0x180013803  mov     [r11+20h], rbx
0x180013807  push    rdi
0x180013808  sub     rsp, 60h
0x18001380c  mov     rax, cs:__security_cookie
0x180013813  xor     rax, rsp
0x180013816  mov     [rsp+68h+var_18], rax
0x18001381b  mov     [r11-38h], r8
0x18001381f  mov     edi, edx
0x180013821  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180013828  mov     ebx, ecx
0x18001382a  jz      short loc_18001384D
0x18001382c  lea     rax, [r11-30h]
0x180013830  mov     r9d, 1
0x180013836  lea     rdx, ApiTetherContact_Start
0x18001383d  mov     [r11-48h], rax
0x180013841  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180013848  call    McGenEventWrite_EtwEventWriteTransfer
0x18001384d  xorps   xmm0, xmm0
0x180013850  mov     [rsp+68h+var_30], 40000044h
0x180013858  movups  [rsp+68h+var_2C], xmm0
0x18001385d  mov     dword ptr [rsp+68h+var_2C], ebx
0x180013861  mov     dword ptr [rsp+68h+var_2C+4], edi
0x180013865  call    cs:__imp_GetThreadDpiAwarenessContext
0x18001386b  mov     rdx, 0FFFFFFFFFFFFFFFDh
0x180013872  lea     rcx, [rsp+68h+var_38]
0x180013877  mov     r8, rax
0x18001387a  call    cs:__imp_TransformPoint
0x180013880  mov     rax, [rsp+68h+var_38]
0x180013885  lea     rdx, [rsp+68h+var_30]; void *
0x18001388a  mov     r8d, 14h; __int16
0x180013890  mov     qword ptr [rsp+68h+var_2C+8], rax
0x180013895  call    ?SendNotification@CApiPortClient@@QEAAJPEAXF@Z; CApiPortClient::SendNotification(void *,short)
0x18001389a  mov     ebx, eax
0x18001389c  test    eax, eax
0x18001389e  jns     short loc_1800138C1
0x1800138a0  mov     r8d, 1; unsigned int
0x1800138a6  mov     [rsp+68h+var_48], 0B1h; unsigned int
0x1800138ae  mov     r9d, eax; int
0x1800138b1  lea     rdx, byte_18001A118; int *
0x1800138b8  lea     ecx, [r8+3]; unsigned int
0x1800138bc  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800138c1  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x1800138c8  jz      short loc_1800138E0
0x1800138ca  mov     r8d, ebx
0x1800138cd  lea     rdx, ApiTetherContact_Stop
0x1800138d4  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x1800138db  call    McTemplateU0q_EtwEventWriteTransfer
0x1800138e0  mov     eax, ebx
0x1800138e2  mov     rcx, [rsp+68h+var_18]
0x1800138e7  xor     rcx, rsp; StackCookie
0x1800138ea  call    __security_check_cookie
0x1800138ef  mov     rbx, [rsp+68h+arg_18]
0x1800138f7  add     rsp, 60h
0x1800138fb  pop     rdi
0x1800138fc  retn
```
