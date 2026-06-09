# RTRegisterUserCert

- ea: `0x180011050`
- end: `0x1800111f6`
- name: `RTRegisterUserCert`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800114c0`

## callees

- `0x180011050`
- `0x180013c74`
- `0x180014458`
- `0x18001d340`
- `0x180023ca0`
- `0x180026010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800110eb`
- `RPCRT4!UuidCreate` at `0x1800110eb`

## pseudocode

```c
__int64 __fastcall RTRegisterUserCert(__int64 *a1, int a2)
{
  int v4; // ebx
  unsigned __int16 v5; // r8
  _DWORD *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  int v10; // eax
  int v12; // [rsp+50h] [rbp-69h] BYREF
  __int64 v13; // [rsp+58h] [rbp-61h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-59h] BYREF
  __int128 v15; // [rsp+70h] [rbp-49h] BYREF
  _DWORD v16[4]; // [rsp+80h] [rbp-39h] BYREF
  _DWORD v17[4]; // [rsp+90h] [rbp-29h] BYREF
  __int16 v18; // [rsp+A0h] [rbp-19h] BYREF
  UUID *p_Uuid; // [rsp+A8h] [rbp-11h]
  __int16 v20; // [rsp+B8h] [rbp-1h]
  int v21; // [rsp+C0h] [rbp+7h]
  __int64 v22; // [rsp+C8h] [rbp+Fh]
  __int16 v23; // [rsp+D0h] [rbp+17h]
  __int128 *v24; // [rsp+D8h] [rbp+1Fh]

  v4 = RtpOneTimeThreadInit();
  if ( v4 < 0 )
  {
    v5 = 1112;
LABEL_14:
    LogMsgHR(v4, (wchar_t *)L"rt/rtcert", v5);
    return (unsigned int)v4;
  }
  v16[0] = 706;
  v16[1] = 702;
  v16[2] = 705;
  v6 = v16;
  v17[0] = 5209;
  if ( a2 )
    v6 = v17;
  v17[1] = 5207;
  v17[2] = 5208;
  p_Uuid = &Uuid;
  v18 = 72;
  Uuid = 0;
  UuidCreate(&Uuid);
  v12 = 0;
  v20 = 65;
  v7 = *a1;
  v13 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, int *))(v7 + 32))(a1, &v13, &v12);
  if ( v4 < 0 )
  {
    v5 = 50;
    goto LABEL_14;
  }
  v21 = v12;
  v22 = v13;
  v8 = *a1;
  v15 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(v8 + 16))(a1, &v15);
  if ( v4 < 0 )
  {
    v5 = 60;
    goto LABEL_14;
  }
  v24 = &v15;
  v23 = 72;
  v10 = ADCreateObject(4, 0, v9, 0, 0, 3, v6, &v18, 0);
  v4 = v10;
  if ( v10 == -1072823027 )
  {
    v4 = -1072824274;
LABEL_13:
    v5 = 70;
    goto LABEL_14;
  }
  if ( v10 < 0 )
    goto LABEL_13;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011050  mov     [rsp-8+arg_8], rbx
0x180011055  mov     [rsp-8+arg_10], rsi
0x18001105a  push    rbp
0x18001105b  push    rdi
0x18001105c  push    r14
0x18001105e  lea     rbp, [rsp-47h]
0x180011063  sub     rsp, 100h
0x18001106a  mov     rax, cs:__security_cookie
0x180011071  xor     rax, rsp
0x180011074  mov     [rbp+57h+var_20], rax
0x180011078  mov     r14d, edx
0x18001107b  mov     rdi, rcx
0x18001107e  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180011083  mov     ebx, eax
0x180011085  test    eax, eax
0x180011087  jns     short loc_180011094
0x180011089  mov     r8d, 458h
0x18001108f  jmp     loc_1800111C2
0x180011094  test    r14d, r14d
0x180011097  mov     [rbp+57h+var_90], 2C2h
0x18001109e  lea     rax, [rbp+57h+var_80]
0x1800110a2  mov     [rbp+57h+var_8C], 2BEh
0x1800110a9  xorps   xmm0, xmm0
0x1800110ac  mov     [rbp+57h+var_88], 2C1h
0x1800110b3  lea     rsi, [rbp+57h+var_90]
0x1800110b7  mov     [rbp+57h+var_80], 1459h
0x1800110be  cmovnz  rsi, rax
0x1800110c2  mov     [rbp+57h+var_7C], 1457h
0x1800110c9  lea     rax, [rbp+57h+Uuid]
0x1800110cd  mov     [rbp+57h+var_78], 1458h
0x1800110d4  mov     r14d, 48h ; 'H'
0x1800110da  mov     [rbp+57h+var_68], rax
0x1800110de  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800110e2  mov     [rbp+57h+var_70], r14w
0x1800110e7  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800110eb  call    cs:__imp_UuidCreate
0x1800110f1  lea     eax, [r14-7]
0x1800110f5  mov     [rbp+57h+var_C0], 0
0x1800110fc  mov     [rbp+57h+var_58], ax
0x180011100  lea     r8, [rbp+57h+var_C0]
0x180011104  mov     rax, [rdi]
0x180011107  lea     rdx, [rbp+57h+var_B8]
0x18001110b  mov     rcx, rdi
0x18001110e  mov     [rbp+57h+var_B8], 0
0x180011116  mov     rax, [rax+20h]
0x18001111a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111f  mov     ebx, eax
0x180011121  test    eax, eax
0x180011123  jns     short loc_18001112E
0x180011125  lea     r8d, [r14-16h]
0x180011129  jmp     loc_1800111C2
0x18001112e  mov     eax, [rbp+57h+var_C0]
0x180011131  lea     rdx, [rbp+57h+var_A0]
0x180011135  mov     [rbp+57h+var_50], eax
0x180011138  xorps   xmm0, xmm0
0x18001113b  mov     rax, [rbp+57h+var_B8]
0x18001113f  mov     rcx, rdi
0x180011142  mov     [rbp+57h+var_48], rax
0x180011146  mov     rax, [rdi]
0x180011149  movups  [rbp+57h+var_A0], xmm0
0x18001114d  mov     rax, [rax+10h]
0x180011151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011156  mov     ebx, eax
0x180011158  test    eax, eax
0x18001115a  jns     short loc_180011164
0x18001115c  mov     r8d, 3Ch ; '<'
0x180011162  jmp     short loc_1800111C2
0x180011164  mov     [rsp+110h+var_D0], 0
0x18001116d  lea     rax, [rbp+57h+var_A0]
0x180011171  mov     [rbp+57h+var_38], rax
0x180011175  xor     edx, edx
0x180011177  lea     rax, [rbp+57h+var_70]
0x18001117b  mov     [rbp+57h+var_40], r14w
0x180011180  mov     [rsp+110h+var_D8], rax
0x180011185  xor     r9d, r9d
0x180011188  mov     [rsp+110h+var_E0], rsi
0x18001118d  mov     [rsp+110h+var_E8], 3
0x180011195  lea     ecx, [rdx+4]
0x180011198  mov     [rsp+110h+var_F0], 0
0x1800111a1  call    ?ADCreateObject@@YAJW4AD_OBJECT@@PEB_W_N1PEAXKQEBKQEBUtagPROPVARIANT@@PEAU_GUID@@@Z; ADCreateObject(AD_OBJECT,wchar_t const *,bool,wchar_t const *,void *,ulong,ulong const * const,tagPROPVARIANT const * const,_GUID *)
0x1800111a6  mov     ebx, eax
0x1800111a8  cmp     eax, 0C00E050Dh
0x1800111ad  jz      short loc_1800111B7
0x1800111af  test    eax, eax
0x1800111b1  jz      short loc_1800111D0
0x1800111b3  jns     short loc_1800111D0
0x1800111b5  jmp     short loc_1800111BC
0x1800111b7  mov     ebx, 0C00E002Eh
0x1800111bc  mov     r8d, 46h ; 'F'; unsigned __int16
0x1800111c2  lea     rdx, aRtRtcert; "rt/rtcert"
0x1800111c9  mov     ecx, ebx; int
0x1800111cb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800111d0  mov     eax, ebx
0x1800111d2  mov     rcx, [rbp+57h+var_20]
0x1800111d6  xor     rcx, rsp; StackCookie
0x1800111d9  call    __security_check_cookie
0x1800111de  lea     r11, [rsp+110h+var_10]
0x1800111e6  mov     rbx, [r11+28h]
0x1800111ea  mov     rsi, [r11+30h]
0x1800111ee  mov     rsp, r11
0x1800111f1  pop     r14
0x1800111f3  pop     rdi
0x1800111f4  pop     rbp
0x1800111f5  retn
```
