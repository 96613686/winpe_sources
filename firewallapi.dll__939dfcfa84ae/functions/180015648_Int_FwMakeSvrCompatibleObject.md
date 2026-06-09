# Int_FwMakeSvrCompatibleObject

- ea: `0x180015648`
- end: `0x1800158e5`
- name: `Int_FwMakeSvrCompatibleObject`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800149f4`

## callees

- `0x180005e0c`
- `0x180015648`
- `0x1800294b0`
- `0x180062010`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180015779`
- `fwbase!FwHResultToWindowsError` at `0x18001582d`
- `fwbase!FwHResultToWindowsError` at `0x1800158a0`
- `fwbase!FwHResultToWindowsError` at `0x180015779`
- `fwbase!FwHResultToWindowsError` at `0x18001582d`
- `fwbase!FwHResultToWindowsError` at `0x1800158a0`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x18001581f`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x180015892`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x18001581f`
- `FWPolicyIOMgr!FwCopyAuthSetToLowerVersion` at `0x180015892`
- `FWPolicyIOMgr!FwFreeSets` at `0x18001586f`
- `FWPolicyIOMgr!FwFreeSets` at `0x18001586f`

## pseudocode

```c
__int64 __fastcall Int_FwMakeSvrCompatibleObject(
        __int64 a1,
        _QWORD *a2,
        unsigned __int16 a3,
        __int64 (__fastcall *a4)(__int64, _QWORD *),
        __int64 (__fastcall *a5)(__int64, int *),
        unsigned __int16 a6,
        int a7,
        _DWORD *a8)
{
  unsigned int v8; // ebx
  unsigned int v14; // eax
  FwPolicy2 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // [rsp+20h] [rbp-58h] BYREF
  int v22; // [rsp+28h] [rbp-50h] BYREF

  v8 = 0;
  v22 = 0x10000;
  v21 = 0;
  *a2 = 0;
  if ( a3 >= 0x221u )
    goto LABEL_2;
  v14 = a5(a1, &v22);
  v8 = v14;
  if ( v14 != 87 && v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v16 = 378;
    goto LABEL_9;
  }
  if ( v22 == 0x40000 )
  {
    v8 = 50;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 379;
      v17 = 50;
      goto LABEL_10;
    }
    return v8;
  }
  if ( v22 != 0x10000 )
  {
    v18 = a4(a1, a2);
    v14 = FwHResultToWindowsError(v18);
    v8 = v14;
    if ( v14 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v16 = 380;
    }
    else
    {
      v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))a5)(*a2, 0, a3);
      v8 = v14;
      if ( !v14 )
        goto LABEL_2;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v8;
      v16 = 381;
    }
LABEL_9:
    v17 = v14;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v17);
    return v8;
  }
LABEL_2:
  if ( a7 == 3 && a6 < 0x214u )
  {
    if ( *a2 )
    {
      v19 = FwCopyAuthSetToLowerVersion(522, *a2, &v21);
      v14 = FwHResultToWindowsError(v19);
      v8 = v14;
      if ( !v14 )
      {
        FwFreeSets(*a2, 0);
        *a2 = v21;
        *a8 = 1;
        return v8;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 382;
        goto LABEL_9;
      }
    }
    else
    {
      v20 = FwCopyAuthSetToLowerVersion(522, a1, &v21);
      v14 = FwHResultToWindowsError(v20);
      v8 = v14;
      if ( !v14 )
      {
        *a2 = v21;
        return v8;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 383;
        goto LABEL_9;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180015648  push    rbx
0x18001564a  push    rbp
0x18001564b  push    rsi
0x18001564c  push    rdi
0x18001564d  push    r12
0x18001564f  push    r14
0x180015651  push    r15
0x180015653  sub     rsp, 40h
0x180015657  mov     rax, cs:__security_cookie
0x18001565e  xor     rax, rsp
0x180015661  mov     [rsp+78h+var_48], rax
0x180015666  mov     r14, [rsp+78h+arg_20]
0x18001566e  xor     ebx, ebx
0x180015670  mov     r15, [rsp+78h+arg_38]
0x180015678  mov     eax, 221h
0x18001567d  mov     [rsp+78h+var_50], 10000h
0x180015685  mov     r12, r9
0x180015688  mov     [rsp+78h+var_58], rbx
0x18001568d  movzx   ebp, r8w
0x180015691  mov     [rdx], rbx
0x180015694  mov     rdi, rdx
0x180015697  mov     rsi, rcx
0x18001569a  cmp     r8w, ax
0x18001569e  jb      short loc_1800156CD
0x1800156a0  cmp     [rsp+78h+arg_30], 3
0x1800156a8  jz      loc_1800157FC
0x1800156ae  mov     eax, ebx
0x1800156b0  mov     rcx, [rsp+78h+var_48]
0x1800156b5  xor     rcx, rsp; StackCookie
0x1800156b8  call    __security_check_cookie
0x1800156bd  add     rsp, 40h
0x1800156c1  pop     r15
0x1800156c3  pop     r14
0x1800156c5  pop     r12
0x1800156c7  pop     rdi
0x1800156c8  pop     rsi
0x1800156c9  pop     rbp
0x1800156ca  pop     rbx
0x1800156cb  retn
0x1800156cd  lea     rdx, [rsp+78h+var_50]
0x1800156d2  mov     rax, r14
0x1800156d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156da  mov     ebx, eax
0x1800156dc  cmp     eax, 57h ; 'W'
0x1800156df  jz      short loc_180015729
0x1800156e1  test    eax, eax
0x1800156e3  jz      short loc_180015729
0x1800156e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156ec  lea     rdx, WPP_GLOBAL_Control
0x1800156f3  cmp     rcx, rdx
0x1800156f6  jz      short loc_1800156AE
0x1800156f8  test    byte ptr [rcx+1Ch], 1
0x1800156fc  jz      short loc_1800156AE
0x1800156fe  mov     edx, 17Ah
0x180015703  jmp     short loc_18001570A
0x180015705  mov     edx, 17Fh
0x18001570a  mov     r9d, eax
0x18001570d  jmp     short loc_180015717
0x18001570f  mov     edx, 17Bh
0x180015714  mov     r9d, ebx
0x180015717  mov     rcx, [rcx+10h]
0x18001571b  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180015722  call    WPP_SF_d
0x180015727  jmp     short loc_1800156AE
0x180015729  cmp     [rsp+78h+var_50], 40000h
0x180015731  jnz     short loc_18001575B
0x180015733  mov     ebx, 32h ; '2'
0x180015738  mov     rcx, cs:WPP_GLOBAL_Control
0x18001573f  lea     rdx, WPP_GLOBAL_Control
0x180015746  cmp     rcx, rdx
0x180015749  jz      loc_1800156AE
0x18001574f  test    byte ptr [rcx+1Ch], 1
0x180015753  jz      loc_1800156AE
0x180015759  jmp     short loc_18001570F
0x18001575b  cmp     [rsp+78h+var_50], 10000h
0x180015763  jz      loc_1800156A0
0x180015769  mov     rdx, rdi
0x18001576c  mov     rcx, rsi
0x18001576f  mov     rax, r12
0x180015772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015777  mov     ecx, eax
0x180015779  call    cs:__imp_FwHResultToWindowsError
0x180015780  nop     dword ptr [rax+rax+00h]
0x180015785  mov     ebx, eax
0x180015787  test    eax, eax
0x180015789  jz      short loc_1800157B6
0x18001578b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015792  lea     rdx, WPP_GLOBAL_Control
0x180015799  cmp     rcx, rdx
0x18001579c  jz      loc_1800156AE
0x1800157a2  test    byte ptr [rcx+1Ch], 1
0x1800157a6  jz      loc_1800156AE
0x1800157ac  mov     edx, 17Ch
0x1800157b1  jmp     loc_18001570A
0x1800157b6  mov     rcx, [rdi]
0x1800157b9  movzx   r8d, bp
0x1800157bd  xor     edx, edx
0x1800157bf  mov     rax, r14
0x1800157c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157c7  mov     ebx, eax
0x1800157c9  test    eax, eax
0x1800157cb  jz      loc_1800156A0
0x1800157d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157d8  lea     rdx, WPP_GLOBAL_Control
0x1800157df  cmp     rcx, rdx
0x1800157e2  jz      loc_1800156AE
0x1800157e8  test    byte ptr [rcx+1Ch], 1
0x1800157ec  jz      loc_1800156AE
0x1800157f2  mov     edx, 17Dh
0x1800157f7  jmp     loc_18001570A
0x1800157fc  mov     eax, 214h
0x180015801  cmp     [rsp+78h+arg_28], ax
0x180015809  jnb     loc_1800156AE
0x18001580f  mov     rdx, [rdi]
0x180015812  lea     ecx, [rax-0Ah]
0x180015815  lea     r8, [rsp+78h+var_58]
0x18001581a  test    rdx, rdx
0x18001581d  jz      short loc_18001588F
0x18001581f  call    cs:__imp_FwCopyAuthSetToLowerVersion
0x180015826  nop     dword ptr [rax+rax+00h]
0x18001582b  mov     ecx, eax
0x18001582d  call    cs:__imp_FwHResultToWindowsError
0x180015834  nop     dword ptr [rax+rax+00h]
0x180015839  mov     ebx, eax
0x18001583b  test    eax, eax
0x18001583d  jz      short loc_18001586A
0x18001583f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015846  lea     rdx, WPP_GLOBAL_Control
0x18001584d  cmp     rcx, rdx
0x180015850  jz      loc_1800156AE
0x180015856  test    byte ptr [rcx+1Ch], 1
0x18001585a  jz      loc_1800156AE
0x180015860  mov     edx, 17Eh
0x180015865  jmp     loc_18001570A
0x18001586a  mov     rcx, [rdi]
0x18001586d  xor     edx, edx
0x18001586f  call    cs:__imp_FwFreeSets
0x180015876  nop     dword ptr [rax+rax+00h]
0x18001587b  mov     rax, [rsp+78h+var_58]
0x180015880  mov     [rdi], rax
0x180015883  mov     dword ptr [r15], 1
0x18001588a  jmp     loc_1800156AE
0x18001588f  mov     rdx, rsi
0x180015892  call    cs:__imp_FwCopyAuthSetToLowerVersion
0x180015899  nop     dword ptr [rax+rax+00h]
0x18001589e  mov     ecx, eax
0x1800158a0  call    cs:__imp_FwHResultToWindowsError
0x1800158a7  nop     dword ptr [rax+rax+00h]
0x1800158ac  mov     ebx, eax
0x1800158ae  test    eax, eax
0x1800158b0  jz      short loc_1800158D8
0x1800158b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158b9  lea     rdx, WPP_GLOBAL_Control
0x1800158c0  cmp     rcx, rdx
0x1800158c3  jz      loc_1800156AE
0x1800158c9  test    byte ptr [rcx+1Ch], 1
0x1800158cd  jz      loc_1800156AE
0x1800158d3  jmp     loc_180015705
0x1800158d8  mov     rax, [rsp+78h+var_58]
0x1800158dd  mov     [rdi], rax
0x1800158e0  jmp     loc_1800156AE
```
