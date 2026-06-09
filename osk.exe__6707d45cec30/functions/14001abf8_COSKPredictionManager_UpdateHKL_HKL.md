# COSKPredictionManager::UpdateHKL(HKL__ *)

- ea: `0x14001abf8`
- end: `0x14001acb9`
- name: `?UpdateHKL@COSKPredictionManager@@QEAAXPEAUHKL__@@@Z`
- size: `193`
- prototype: `void __fastcall(COSKPredictionManager *__hidden this, HKL)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140010c78`

## callees

- `0x140013f04`
- `0x14001a2b4`
- `0x14001ab70`
- `0x14001abf8`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001ac67`
- `KERNEL32!GetLastError` at `0x14001ac67`
- `KERNEL32!LCIDToLocaleName` at `0x14001ac35`
- `KERNEL32!LCIDToLocaleName` at `0x14001ac35`

## pseudocode

```c
void __fastcall COSKPredictionManager::UpdateHKL(COSKPredictionManager *this, HKL a2)
{
  unsigned int v3; // edi
  DWORD LastError; // eax
  WCHAR Name[88]; // [rsp+30h] [rbp-C8h] BYREF

  if ( *((HKL *)this + 2) != a2 )
  {
    v3 = (unsigned __int16)a2;
    *((_QWORD *)this + 2) = a2;
    if ( LCIDToLocaleName((unsigned __int16)a2, Name, 85, 0) <= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_8ca0bf681196307d479db2488c079cf4_Traceguids,
          v3,
          LastError);
      }
    }
    else
    {
      COSKPredictionManager::InitializePredictionsBasedOnLocale(this, Name);
    }
    COSKPredictionManager::ResetPredictionKeys(this);
  }
}

```

## disassembly

```asm
0x14001abf8  mov     [rsp+arg_8], rbx
0x14001abfd  push    rdi
0x14001abfe  sub     rsp, 0F0h
0x14001ac05  mov     rax, cs:__security_cookie
0x14001ac0c  xor     rax, rsp
0x14001ac0f  mov     [rsp+0F8h+var_18], rax
0x14001ac17  mov     rbx, rcx
0x14001ac1a  cmp     [rcx+10h], rdx
0x14001ac1e  jz      short loc_14001AC98
0x14001ac20  movzx   edi, dx
0x14001ac23  xor     r9d, r9d; dwFlags
0x14001ac26  mov     [rcx+10h], rdx
0x14001ac2a  lea     rdx, [rsp+0F8h+Name]; lpName
0x14001ac2f  mov     ecx, edi; Locale
0x14001ac31  lea     r8d, [r9+55h]; cchName
0x14001ac35  call    cs:__imp_LCIDToLocaleName
0x14001ac3b  test    eax, eax
0x14001ac3d  jle     short loc_14001AC4E
0x14001ac3f  lea     rdx, [rsp+0F8h+Name]; unsigned __int16 *
0x14001ac44  mov     rcx, rbx; this
0x14001ac47  call    ?InitializePredictionsBasedOnLocale@COSKPredictionManager@@AEAAXPEAG@Z; COSKPredictionManager::InitializePredictionsBasedOnLocale(ushort *)
0x14001ac4c  jmp     short loc_14001AC90
0x14001ac4e  mov     rax, cs:WPP_GLOBAL_Control
0x14001ac55  lea     rcx, WPP_GLOBAL_Control
0x14001ac5c  cmp     rax, rcx
0x14001ac5f  jz      short loc_14001AC90
0x14001ac61  test    byte ptr [rax+1Ch], 1
0x14001ac65  jz      short loc_14001AC90
0x14001ac67  call    cs:__imp_GetLastError
0x14001ac6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac74  lea     r8, WPP_8ca0bf681196307d479db2488c079cf4_Traceguids
0x14001ac7b  mov     edx, 1Ch
0x14001ac80  mov     [rsp+0F8h+var_D8], eax
0x14001ac84  mov     r9d, edi
0x14001ac87  mov     rcx, [rcx+10h]
0x14001ac8b  call    WPP_SF_Dd
0x14001ac90  mov     rcx, rbx; this
0x14001ac93  call    ?ResetPredictionKeys@COSKPredictionManager@@AEAAXXZ; COSKPredictionManager::ResetPredictionKeys(void)
0x14001ac98  mov     rcx, [rsp+0F8h+var_18]
0x14001aca0  xor     rcx, rsp; StackCookie
0x14001aca3  call    __security_check_cookie
0x14001aca8  mov     rbx, [rsp+0F8h+arg_8]
0x14001acb0  add     rsp, 0F0h
0x14001acb7  pop     rdi
0x14001acb8  retn
```
