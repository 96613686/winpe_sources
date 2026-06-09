# MSMSendOneXEventNotification

- ea: `0x1800127a0`
- end: `0x1800129a8`
- name: `MSMSendOneXEventNotification`
- size: `520`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x180005b00`
- `0x18000dd40`
- `0x180012070`
- `0x180012478`
- `0x180012660`
- `0x180015f90`
- `0x18002830c`

## callees

- `0x180005440`
- `0x18000c5a0`
- `0x1800127a0`
- `0x1800179c0`
- `0x1800195a0`
- `0x180020250`
- `0x1800214f0`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001289f`
- `MobileNetworking!ReleaseWriteLock` at `0x18001289f`
- `MobileNetworking!AcquireWriteLock` at `0x180012919`
- `MobileNetworking!AcquireWriteLock` at `0x180012919`

## pseudocode

```c
__int64 __fastcall MSMSendOneXEventNotification(__int64 a1, unsigned int a2, int a3, __int64 a4)
{
  int v4; // r13d
  __int64 v5; // r14
  __int64 v6; // r15
  char *v11; // rcx
  __int64 v12; // rbx
  __int64 NotificationDescription; // rax
  int v14; // eax
  char v15; // bp
  __int64 v16; // rbx
  __int64 v17; // rax
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rbx
  __int64 v21; // rax
  __int128 v23; // [rsp+30h] [rbp-78h] BYREF
  __int128 v24; // [rsp+40h] [rbp-68h]
  __int64 v25; // [rsp+50h] [rbp-58h]

  v4 = *(_DWORD *)(a1 + 20);
  v5 = *(_QWORD *)(a1 + 192);
  v6 = *(_QWORD *)(a1 + 2368);
  v23 = 0;
  v25 = 0;
  v24 = 0;
  v11 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(a1 + 2344) )
  {
    if ( v11 != (char *)&WPP_GLOBAL_Control && v11[68] < 0 )
    {
      v12 = *((_QWORD *)v11 + 7);
      NotificationDescription = GetNotificationDescription(a2);
      WPP_SF_dS(v12, 21, (unsigned int)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4, NotificationDescription);
    }
    LODWORD(v23) = 4;
    DWORD1(v23) = a2;
    DWORD2(v24) = a3;
    v25 = a4;
    ReleaseWriteLock(a1, a1 + 2896, "MSMSendOneXEventNotification", 164);
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *))(a1 + 2344))(v5, v6, &v23);
    v15 = v14;
    if ( v14 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v16 = *((_QWORD *)WPP_GLOBAL_Control + 7);
      v17 = GetNotificationDescription(a2);
      WPP_SF_dSd(v16, v18, v19, v4, v17, v15);
    }
    AcquireWriteLock(a1, a1 + 2896, "MSMSendOneXEventNotification", 199);
    goto LABEL_16;
  }
  if ( v11 == (char *)&WPP_GLOBAL_Control )
    return 0;
  if ( v11[68] < 0 )
  {
    v20 = *((_QWORD *)v11 + 7);
    v21 = GetNotificationDescription(a2);
    WPP_SF_dS(v20, 23, (unsigned int)WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v4, v21);
LABEL_16:
    v11 = (char *)WPP_GLOBAL_Control;
  }
  if ( v11 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v11 + 7), 24, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800127a0  push    rbx
0x1800127a2  push    rbp
0x1800127a3  push    rsi
0x1800127a4  push    rdi
0x1800127a5  push    r12
0x1800127a7  push    r13
0x1800127a9  push    r14
0x1800127ab  push    r15
0x1800127ad  sub     rsp, 68h
0x1800127b1  mov     rax, cs:__security_cookie
0x1800127b8  xor     rax, rsp
0x1800127bb  mov     [rsp+0A8h+var_50], rax
0x1800127c0  mov     r13d, [rcx+14h]
0x1800127c4  xorps   xmm0, xmm0
0x1800127c7  mov     r14, [rcx+0C0h]
0x1800127ce  xor     eax, eax
0x1800127d0  mov     r15, [rcx+940h]
0x1800127d7  mov     rbp, r9
0x1800127da  movups  [rsp+0A8h+var_78], xmm0
0x1800127df  mov     [rsp+0A8h+var_58], rax
0x1800127e4  mov     esi, r8d
0x1800127e7  movups  [rsp+0A8h+var_68], xmm0
0x1800127ec  mov     r12d, edx
0x1800127ef  mov     rdi, rcx
0x1800127f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127f9  lea     rbx, WPP_GLOBAL_Control
0x180012800  cmp     rcx, rbx
0x180012803  jz      short loc_18001282A
0x180012805  test    dword ptr [rcx+44h], 800h
0x18001280c  jz      short loc_18001282A
0x18001280e  mov     rcx, [rcx+38h]
0x180012812  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180012819  mov     edx, 14h
0x18001281e  call    WPP_SF_
0x180012823  mov     rcx, cs:WPP_GLOBAL_Control
0x18001282a  cmp     qword ptr [rdi+928h], 0
0x180012832  jz      loc_180012921
0x180012838  cmp     rcx, rbx
0x18001283b  jz      short loc_180012872
0x18001283d  test    byte ptr [rcx+44h], 80h
0x180012841  jz      short loc_180012872
0x180012843  mov     rbx, [rcx+38h]
0x180012847  mov     ecx, r12d
0x18001284a  call    GetNotificationDescription
0x18001284f  mov     edx, 15h
0x180012854  mov     [rsp+0A8h+var_88], rax
0x180012859  mov     r9d, r13d
0x18001285c  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180012863  mov     rcx, rbx
0x180012866  call    WPP_SF_dS
0x18001286b  lea     rbx, WPP_GLOBAL_Control
0x180012872  mov     r9d, 0A4h
0x180012878  mov     dword ptr [rsp+0A8h+var_78], 4
0x180012880  lea     r8, aMsmsendonexeve; "MSMSendOneXEventNotification"
0x180012887  mov     dword ptr [rsp+0A8h+var_78+4], r12d
0x18001288c  lea     rdx, [rdi+0B50h]
0x180012893  mov     dword ptr [rsp+0A8h+var_68+8], esi
0x180012897  mov     rcx, rdi
0x18001289a  mov     [rsp+0A8h+var_58], rbp
0x18001289f  call    cs:__imp_ReleaseWriteLock
0x1800128a5  mov     rax, [rdi+928h]
0x1800128ac  lea     r8, [rsp+0A8h+var_78]
0x1800128b1  mov     rdx, r15
0x1800128b4  mov     rcx, r14
0x1800128b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128bc  mov     ebp, eax
0x1800128be  test    eax, eax
0x1800128c0  jz      short loc_180012902
0x1800128c2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800128c9  lea     rax, WPP_GLOBAL_Control
0x1800128d0  cmp     rbx, rax
0x1800128d3  jz      short loc_1800128FB
0x1800128d5  test    byte ptr [rbx+44h], 1
0x1800128d9  jz      short loc_1800128FB
0x1800128db  mov     rbx, [rbx+38h]
0x1800128df  mov     ecx, r12d
0x1800128e2  call    GetNotificationDescription
0x1800128e7  mov     r9d, r13d
0x1800128ea  mov     [rsp+0A8h+var_80], ebp
0x1800128ee  mov     rcx, rbx
0x1800128f1  mov     [rsp+0A8h+var_88], rax
0x1800128f6  call    WPP_SF_dSd
0x1800128fb  lea     rbx, WPP_GLOBAL_Control
0x180012902  mov     r9d, 0C7h
0x180012908  lea     r8, aMsmsendonexeve; "MSMSendOneXEventNotification"
0x18001290f  lea     rdx, [rdi+0B50h]
0x180012916  mov     rcx, rdi
0x180012919  call    cs:__imp_AcquireWriteLock
0x18001291f  jmp     short loc_18001295B
0x180012921  cmp     rcx, rbx
0x180012924  jz      short loc_180012988
0x180012926  test    byte ptr [rcx+44h], 80h
0x18001292a  jz      short loc_180012962
0x18001292c  mov     rbx, [rcx+38h]
0x180012930  mov     ecx, r12d
0x180012933  call    GetNotificationDescription
0x180012938  mov     edx, 17h
0x18001293d  mov     [rsp+0A8h+var_88], rax
0x180012942  mov     r9d, r13d
0x180012945  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001294c  mov     rcx, rbx
0x18001294f  call    WPP_SF_dS
0x180012954  lea     rbx, WPP_GLOBAL_Control
0x18001295b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012962  cmp     rcx, rbx
0x180012965  jz      short loc_180012988
0x180012967  test    dword ptr [rcx+44h], 800h
0x18001296e  jz      short loc_180012988
0x180012970  mov     rcx, [rcx+38h]
0x180012974  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18001297b  mov     edx, 18h
0x180012980  xor     r9d, r9d
0x180012983  call    WPP_SF_D
0x180012988  xor     eax, eax
0x18001298a  mov     rcx, [rsp+0A8h+var_50]
0x18001298f  xor     rcx, rsp; StackCookie
0x180012992  call    __security_check_cookie
0x180012997  add     rsp, 68h
0x18001299b  pop     r15
0x18001299d  pop     r14
0x18001299f  pop     r13
0x1800129a1  pop     r12
0x1800129a3  pop     rdi
0x1800129a4  pop     rsi
0x1800129a5  pop     rbp
0x1800129a6  pop     rbx
0x1800129a7  retn
```
