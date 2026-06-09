# PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180027474`
- end: `0x180027696`
- name: `?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017498`

## callees

- `0x180002890`
- `0x180003830`
- `0x180003e34`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180027474`
- `0x1800385e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002766b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002766b`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x1800275a6`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x1800275a6`

## pseudocode

```c
__int64 __fastcall PackageUtility::GetProcessApplicationId(HANDLE ProcessHandle, __int64 a2)
{
  void *v4; // rdi
  unsigned __int16 **v5; // r8
  int ProcessAppId; // eax
  int PackageIdentity; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v12; // [rsp+30h] [rbp-148h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-140h] BYREF
  _BYTE v14[272]; // [rsp+40h] [rbp-138h] BYREF

  v4 = 0;
  v12 = 0;
  if ( !ProcessHandle || !a2 )
  {
    PackageIdentity = -2147024809;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_33;
    v10 = 15;
    goto LABEL_32;
  }
  if ( (unsigned __int8)IsGetPackageFullNamePresent() )
  {
    pv = 0;
    ProcessAppId = CallerIdentity::GetProcessAppId(ProcessHandle, &pv, v5);
    PackageIdentity = ProcessAppId;
    if ( ProcessAppId < 0 )
    {
      if ( ProcessAppId != -2147023728
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_426532d07a9735b83ad974c5a485a15d_Traceguids,
          (unsigned int)ProcessAppId);
      }
      v4 = pv;
      goto LABEL_33;
    }
    v4 = pv;
    if ( pv )
    {
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)pv + v8) );
    }
    else
    {
      v8 = 0;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             a2,
                             pv,
                             v8) )
    {
      PackageIdentity = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v10 = 17;
      goto LABEL_32;
    }
LABEL_28:
    PackageIdentity = 0;
    goto LABEL_33;
  }
  if ( !(unsigned __int8)IsXerGetPackageIdentityPresent() )
    goto LABEL_28;
  v12 = 131;
  PackageIdentity = XerGetPackageIdentity(ProcessHandle, 0, 0, &v12, v14);
  if ( PackageIdentity >= 0 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            a2,
                            v14,
                            (unsigned int)(v12 - 1)) )
      goto LABEL_28;
    PackageIdentity = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_33;
    v10 = 19;
LABEL_32:
    WPP_SF_(v9[2], v10, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids);
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_426532d07a9735b83ad974c5a485a15d_Traceguids,
      (unsigned int)PackageIdentity);
LABEL_33:
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)PackageIdentity;
}

```

## disassembly

```asm
0x180027474  mov     [rsp+arg_10], rbx
0x180027479  push    rbp
0x18002747a  push    rsi
0x18002747b  push    rdi
0x18002747c  sub     rsp, 160h
0x180027483  mov     rax, cs:__security_cookie
0x18002748a  xor     rax, rsp
0x18002748d  mov     [rsp+178h+var_28], rax
0x180027495  mov     rsi, rdx
0x180027498  mov     rbx, rcx
0x18002749b  xor     ebp, ebp
0x18002749d  mov     edi, ebp
0x18002749f  mov     [rsp+178h+var_148], ebp
0x1800274a3  test    rcx, rcx
0x1800274a6  jz      loc_18002762F
0x1800274ac  test    rdx, rdx
0x1800274af  jz      loc_18002762F
0x1800274b5  call    IsGetPackageFullNamePresent
0x1800274ba  test    al, al
0x1800274bc  jz      loc_18002757A
0x1800274c2  mov     [rsp+178h+pv], rbp
0x1800274c7  lea     rdx, [rsp+178h+pv]; void *
0x1800274cc  mov     rcx, rbx; ProcessHandle
0x1800274cf  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800274d4  mov     ebx, eax
0x1800274d6  test    eax, eax
0x1800274d8  jns     short loc_18002751A
0x1800274da  cmp     eax, 80070490h
0x1800274df  jz      short loc_180027510
0x1800274e1  lea     rax, WPP_GLOBAL_Control
0x1800274e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274ef  cmp     rcx, rax
0x1800274f2  jz      short loc_180027510
0x1800274f4  test    byte ptr [rcx+1Ch], 1
0x1800274f8  jz      short loc_180027510
0x1800274fa  lea     edx, [rbp+10h]
0x1800274fd  mov     r9d, ebx
0x180027500  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x180027507  mov     rcx, [rcx+10h]
0x18002750b  call    WPP_SF_d
0x180027510  mov     rdi, [rsp+178h+pv]
0x180027515  jmp     loc_180027663
0x18002751a  mov     rdi, [rsp+178h+pv]
0x18002751f  test    rdi, rdi
0x180027522  jz      short loc_180027534
0x180027524  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027528  inc     r8
0x18002752b  cmp     [rdi+r8*2], bp
0x180027530  jnz     short loc_180027528
0x180027532  jmp     short loc_180027537
0x180027534  mov     r8, rbp
0x180027537  mov     rdx, rdi
0x18002753a  mov     rcx, rsi
0x18002753d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180027542  test    al, al
0x180027544  jnz     loc_18002762B
0x18002754a  mov     ebx, 8007000Eh
0x18002754f  lea     rax, WPP_GLOBAL_Control
0x180027556  mov     rcx, cs:WPP_GLOBAL_Control
0x18002755d  cmp     rcx, rax
0x180027560  jz      loc_180027663
0x180027566  test    byte ptr [rcx+1Ch], 1
0x18002756a  jz      loc_180027663
0x180027570  mov     edx, 11h
0x180027575  jmp     loc_180027652
0x18002757a  call    IsXerGetPackageIdentityPresent
0x18002757f  test    al, al
0x180027581  jz      loc_18002762B
0x180027587  mov     [rsp+178h+var_148], 83h
0x18002758f  lea     rax, [rsp+178h+var_138]
0x180027594  mov     [rsp+178h+var_158], rax
0x180027599  lea     r9, [rsp+178h+var_148]
0x18002759e  xor     r8d, r8d
0x1800275a1  xor     edx, edx
0x1800275a3  mov     rcx, rbx
0x1800275a6  call    cs:__imp_XerGetPackageIdentity
0x1800275ac  mov     ebx, eax
0x1800275ae  test    eax, eax
0x1800275b0  jns     short loc_1800275ED
0x1800275b2  lea     rax, WPP_GLOBAL_Control
0x1800275b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275c0  cmp     rcx, rax
0x1800275c3  jz      loc_180027663
0x1800275c9  test    byte ptr [rcx+1Ch], 1
0x1800275cd  jz      loc_180027663
0x1800275d3  mov     edx, 12h
0x1800275d8  mov     r9d, ebx
0x1800275db  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800275e2  mov     rcx, [rcx+10h]
0x1800275e6  call    WPP_SF_d
0x1800275eb  jmp     short loc_180027663
0x1800275ed  mov     r8d, [rsp+178h+var_148]
0x1800275f2  dec     r8d
0x1800275f5  lea     rdx, [rsp+178h+var_138]
0x1800275fa  mov     rcx, rsi
0x1800275fd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180027602  test    al, al
0x180027604  jnz     short loc_18002762B
0x180027606  mov     ebx, 8007000Eh
0x18002760b  lea     rax, WPP_GLOBAL_Control
0x180027612  mov     rcx, cs:WPP_GLOBAL_Control
0x180027619  cmp     rcx, rax
0x18002761c  jz      short loc_180027663
0x18002761e  test    byte ptr [rcx+1Ch], 1
0x180027622  jz      short loc_180027663
0x180027624  mov     edx, 13h
0x180027629  jmp     short loc_180027652
0x18002762b  mov     ebx, ebp
0x18002762d  jmp     short loc_180027663
0x18002762f  mov     ebx, 80070057h
0x180027634  lea     rax, WPP_GLOBAL_Control
0x18002763b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027642  cmp     rcx, rax
0x180027645  jz      short loc_180027663
0x180027647  test    byte ptr [rcx+1Ch], 1
0x18002764b  jz      short loc_180027663
0x18002764d  mov     edx, 0Fh
0x180027652  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x180027659  mov     rcx, [rcx+10h]
0x18002765d  call    WPP_SF_
0x180027662  nop
0x180027663  test    rdi, rdi
0x180027666  jz      short loc_180027671
0x180027668  mov     rcx, rdi; pv
0x18002766b  call    cs:__imp_CoTaskMemFree
0x180027671  mov     eax, ebx
0x180027673  mov     rcx, [rsp+178h+var_28]
0x18002767b  xor     rcx, rsp; StackCookie
0x18002767e  call    __security_check_cookie
0x180027683  mov     rbx, [rsp+178h+arg_10]
0x18002768b  add     rsp, 160h
0x180027692  pop     rdi
0x180027693  pop     rsi
0x180027694  pop     rbp
0x180027695  retn
```
