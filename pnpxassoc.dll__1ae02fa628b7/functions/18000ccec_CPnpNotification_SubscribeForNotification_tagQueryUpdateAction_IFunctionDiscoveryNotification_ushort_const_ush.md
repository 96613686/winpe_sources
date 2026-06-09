# CPnpNotification::SubscribeForNotification(tagQueryUpdateAction,IFunctionDiscoveryNotification *,ushort const *,ushort const *,ulong,CChildDeviceInfo *)

- ea: `0x18000ccec`
- end: `0x18000cf4e`
- name: `?SubscribeForNotification@CPnpNotification@@QEAAJW4tagQueryUpdateAction@@PEAUIFunctionDiscoveryNotification@@PEBG2KPEAVCChildDeviceInfo@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(CPnpNotification *__hidden this, enum tagQueryUpdateAction, struct IFunctionDiscoveryNotification *, const unsigned __int16 *, wchar_t *String1, unsigned int, struct CChildDeviceInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18000a28c`

## callees

- `0x1800019d4`
- `0x18000bae8`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000c33c`
- `0x18000ccec`
- `0x18000d16c`
- `0x180012dce`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ce41`
- `KERNEL32!GetLastError` at `0x18000ce41`
- `KERNEL32!LeaveCriticalSection` at `0x18000cea5`
- `KERNEL32!LeaveCriticalSection` at `0x18000cea5`
- `KERNEL32!EnterCriticalSection` at `0x18000ce82`
- `KERNEL32!EnterCriticalSection` at `0x18000ce82`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000ce37`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000ce37`

## pseudocode

```c
__int64 __fastcall CPnpNotification::SubscribeForNotification(
        CPnpNotification *this,
        enum tagQueryUpdateAction a2,
        struct IFunctionDiscoveryNotification *a3,
        const unsigned __int16 *a4,
        wchar_t *String1,
        unsigned int a6,
        struct CChildDeviceInfo *a7)
{
  CPnpNotification *v7; // rbp
  _BYTE *v11; // rcx
  __int64 v12; // rdx
  void **v13; // rax
  void **v14; // rsi
  unsigned int v15; // edi
  signed int LastError; // eax
  void ***v17; // rax
  _QWORD *v18; // rcx
  int v19; // eax
  bool v20; // cf

  v7 = g_pPnpNotification;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a3 || !a4 || !String1 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147942487LL;
    v12 = 36;
    goto LABEL_33;
  }
  if ( !a6 && a7 || !a7 && a6 )
  {
    if ( v11 == (_BYTE *)&WPP_GLOBAL_Control || v11[25] < 2u )
      return 2147942487LL;
    v12 = 37;
LABEL_33:
    WPP_SF_sqd(*((_QWORD *)v11 + 2), v12, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    return 2147942487LL;
  }
  CPnpNotification::Unsubscribe(v7, String1);
  v13 = (void **)operator new(0x58u);
  v14 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 0x58u);
    v15 = MyDuplicateString(a4, v14 + 2);
    if ( !v15 )
    {
      v15 = MyDuplicateString(String1, v14 + 3);
      if ( !v15 )
      {
        if ( CreateTimerQueueTimer(v14 + 4, 0, CPnpNotification::TimerCallback, v14, 0x7530u, 0x7530u, 1u) )
          goto LABEL_21;
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( !v15 )
        {
LABEL_21:
          ((void (__fastcall *)(struct IFunctionDiscoveryNotification *))a3->lpVtbl->AddRef)(a3);
          v14[5] = a3;
          v14[6] = v7;
          *((_DWORD *)v14 + 16) = a6;
          v14[9] = a7;
          *((_DWORD *)v14 + 20) = a2;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 72));
          v17 = (void ***)*((_QWORD *)v7 + 17);
          *v14 = (char *)v7 + 128;
          v14[1] = v17;
          *v17 = v14;
          *((_QWORD *)v7 + 17) = v14;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 72));
          v18 = WPP_GLOBAL_Control;
          v19 = 0;
          v20 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
          goto LABEL_26;
        }
      }
    }
    CPnpNotification::FreeNotificationItem(v7, (struct _NOTIFICATION_ITEM *)v14);
  }
  else
  {
    v15 = -2147024882;
  }
  v18 = WPP_GLOBAL_Control;
  v19 = 0;
  v20 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
LABEL_26:
  if ( v18 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v19) = !v20;
    if ( v19 )
      WPP_SF_sqd(v18[2], 38, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  }
  return v15;
}

```

## disassembly

```asm
0x18000ccec  push    rbx
0x18000ccee  push    rbp
0x18000ccef  push    rsi
0x18000ccf0  push    rdi
0x18000ccf1  push    r12
0x18000ccf3  push    r13
0x18000ccf5  push    r14
0x18000ccf7  push    r15
0x18000ccf9  sub     rsp, 48h
0x18000ccfd  mov     rbp, cs:?g_pPnpNotification@@3PEAVCPnpNotification@@EA; CPnpNotification * g_pPnpNotification
0x18000cd04  mov     rdi, r9
0x18000cd07  mov     r12, r8
0x18000cd0a  mov     r13d, edx
0x18000cd0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd14  lea     rax, WPP_GLOBAL_Control
0x18000cd1b  cmp     rcx, rax
0x18000cd1e  jz      short loc_18000CD4E
0x18000cd20  cmp     byte ptr [rcx+19h], 4
0x18000cd24  jb      short loc_18000CD4E
0x18000cd26  mov     rcx, [rcx+10h]
0x18000cd2a  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000cd31  mov     edx, 23h ; '#'
0x18000cd36  mov     qword ptr [rsp+88h+DueTime], rbp
0x18000cd3b  call    WPP_SF_sq
0x18000cd40  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd47  lea     rax, WPP_GLOBAL_Control
0x18000cd4e  mov     esi, 80070057h
0x18000cd53  test    r12, r12
0x18000cd56  jz      loc_18000CF12
0x18000cd5c  test    rdi, rdi
0x18000cd5f  jz      loc_18000CF12
0x18000cd65  mov     rbx, [rsp+88h+String1]
0x18000cd6d  test    rbx, rbx
0x18000cd70  jz      loc_18000CF12
0x18000cd76  mov     r15d, [rsp+88h+arg_28]
0x18000cd7e  mov     r14, [rsp+88h+arg_30]
0x18000cd86  test    r15d, r15d
0x18000cd89  jnz     short loc_18000CD90
0x18000cd8b  test    r14, r14
0x18000cd8e  jnz     short loc_18000CD9A
0x18000cd90  test    r14, r14
0x18000cd93  jnz     short loc_18000CDB7
0x18000cd95  test    r15d, r15d
0x18000cd98  jz      short loc_18000CDB7
0x18000cd9a  cmp     rcx, rax
0x18000cd9d  jz      loc_18000CF3B
0x18000cda3  cmp     byte ptr [rcx+19h], 2
0x18000cda7  jb      loc_18000CF3B
0x18000cdad  mov     edx, 25h ; '%'
0x18000cdb2  jmp     loc_18000CF22
0x18000cdb7  mov     rdx, rbx; String1
0x18000cdba  mov     rcx, rbp; this
0x18000cdbd  call    ?Unsubscribe@CPnpNotification@@QEAAJPEBG@Z; CPnpNotification::Unsubscribe(ushort const *)
0x18000cdc2  mov     ecx, 58h ; 'X'; Size
0x18000cdc7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cdcc  mov     rsi, rax
0x18000cdcf  test    rax, rax
0x18000cdd2  jz      loc_18000CECB
0x18000cdd8  xor     edx, edx; Val
0x18000cdda  mov     rcx, rax; void *
0x18000cddd  lea     r8d, [rdx+58h]; Size
0x18000cde1  call    memset_0
0x18000cde6  lea     rdx, [rsi+10h]
0x18000cdea  mov     rcx, rdi
0x18000cded  call    _MyDuplicateString
0x18000cdf2  mov     edi, eax
0x18000cdf4  test    eax, eax
0x18000cdf6  jnz     loc_18000CEAD
0x18000cdfc  lea     rdx, [rsi+18h]
0x18000ce00  mov     rcx, rbx
0x18000ce03  call    _MyDuplicateString
0x18000ce08  mov     edi, eax
0x18000ce0a  test    eax, eax
0x18000ce0c  jnz     loc_18000CEAD
0x18000ce12  mov     eax, 7530h
0x18000ce17  mov     [rsp+88h+Flags], 1; Flags
0x18000ce1f  mov     [rsp+88h+Period], eax; Period
0x18000ce23  lea     rcx, [rsi+20h]; phNewTimer
0x18000ce27  mov     r9, rsi; Parameter
0x18000ce2a  mov     [rsp+88h+DueTime], eax; DueTime
0x18000ce2e  lea     r8, ?TimerCallback@CPnpNotification@@KAXPEAXE@Z; Callback
0x18000ce35  xor     edx, edx; TimerQueue
0x18000ce37  call    cs:__imp_CreateTimerQueueTimer
0x18000ce3d  test    eax, eax
0x18000ce3f  jnz     short loc_18000CE5A
0x18000ce41  call    cs:__imp_GetLastError
0x18000ce47  mov     edi, eax
0x18000ce49  test    eax, eax
0x18000ce4b  jle     short loc_18000CE56
0x18000ce4d  movzx   edi, ax
0x18000ce50  or      edi, 80070000h
0x18000ce56  test    edi, edi
0x18000ce58  jnz     short loc_18000CEAD
0x18000ce5a  mov     rax, [r12]
0x18000ce5e  mov     rcx, r12
0x18000ce61  mov     rax, [rax+8]
0x18000ce65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce6a  lea     rcx, [rbp+48h]; lpCriticalSection
0x18000ce6e  mov     [rsi+28h], r12
0x18000ce72  mov     [rsi+30h], rbp
0x18000ce76  mov     [rsi+40h], r15d
0x18000ce7a  mov     [rsi+48h], r14
0x18000ce7e  mov     [rsi+50h], r13d
0x18000ce82  call    cs:__imp_EnterCriticalSection
0x18000ce88  lea     rdx, [rbp+80h]
0x18000ce8f  mov     rax, [rdx+8]
0x18000ce93  lea     rcx, [rbp+48h]; lpCriticalSection
0x18000ce97  mov     [rsi], rdx
0x18000ce9a  mov     [rsi+8], rax
0x18000ce9e  mov     [rax], rsi
0x18000cea1  mov     [rdx+8], rsi
0x18000cea5  call    cs:__imp_LeaveCriticalSection
0x18000ceab  jmp     short loc_18000CEBC
0x18000cead  mov     rdx, rsi; struct _NOTIFICATION_ITEM *
0x18000ceb0  mov     rcx, rbp; this
0x18000ceb3  call    ?FreeNotificationItem@CPnpNotification@@IEAAXPEAU_NOTIFICATION_ITEM@@@Z; CPnpNotification::FreeNotificationItem(_NOTIFICATION_ITEM *)
0x18000ceb8  test    edi, edi
0x18000ceba  jnz     short loc_18000CED0
0x18000cebc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cec3  xor     eax, eax
0x18000cec5  cmp     byte ptr [rcx+19h], 4
0x18000cec9  jmp     short loc_18000CEDD
0x18000cecb  mov     edi, 8007000Eh
0x18000ced0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ced7  xor     eax, eax
0x18000ced9  cmp     byte ptr [rcx+19h], 2
0x18000cedd  setnb   al
0x18000cee0  lea     rdx, WPP_GLOBAL_Control
0x18000cee7  cmp     rcx, rdx
0x18000ceea  jz      short loc_18000CF0E
0x18000ceec  test    eax, eax
0x18000ceee  jz      short loc_18000CF0E
0x18000cef0  mov     rcx, [rcx+10h]
0x18000cef4  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000cefb  mov     edx, 26h ; '&'
0x18000cf00  mov     [rsp+88h+Period], edi
0x18000cf04  mov     qword ptr [rsp+88h+DueTime], rbp
0x18000cf09  call    WPP_SF_sqd
0x18000cf0e  mov     eax, edi
0x18000cf10  jmp     short loc_18000CF3D
0x18000cf12  cmp     rcx, rax
0x18000cf15  jz      short loc_18000CF3B
0x18000cf17  cmp     byte ptr [rcx+19h], 2
0x18000cf1b  jb      short loc_18000CF3B
0x18000cf1d  mov     edx, 24h ; '$'
0x18000cf22  mov     rcx, [rcx+10h]
0x18000cf26  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000cf2d  mov     [rsp+88h+Period], esi
0x18000cf31  mov     qword ptr [rsp+88h+DueTime], rbp
0x18000cf36  call    WPP_SF_sqd
0x18000cf3b  mov     eax, esi
0x18000cf3d  add     rsp, 48h
0x18000cf41  pop     r15
0x18000cf43  pop     r14
0x18000cf45  pop     r13
0x18000cf47  pop     r12
0x18000cf49  pop     rdi
0x18000cf4a  pop     rsi
0x18000cf4b  pop     rbp
0x18000cf4c  pop     rbx
0x18000cf4d  retn
```
