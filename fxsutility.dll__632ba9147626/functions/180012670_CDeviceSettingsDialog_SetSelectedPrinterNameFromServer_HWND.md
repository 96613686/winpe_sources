# CDeviceSettingsDialog::SetSelectedPrinterNameFromServer(HWND__ *)

- ea: `0x180012670`
- end: `0x18001283b`
- name: `?SetSelectedPrinterNameFromServer@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@@Z`
- size: `459`
- prototype: `unsigned int(CDeviceSettingsDialog *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010bc8`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180012670`

## import_xrefs

- `FXSAPI!FaxGetExtensionDataW` at `0x1800126f3`
- `FXSAPI!FaxGetExtensionDataW` at `0x1800126f3`
- `FXSAPI!FaxFreeBuffer` at `0x180012802`
- `FXSAPI!FaxFreeBuffer` at `0x180012802`
- `KERNEL32!lstrcmpiW` at `0x1800127bd`
- `KERNEL32!lstrcmpiW` at `0x1800127bd`
- `KERNEL32!GetLastError` at `0x1800126fd`
- `KERNEL32!GetLastError` at `0x1800126fd`
- `USER32!SendMessageW` at `0x1800127db`
- `USER32!SendMessageW` at `0x180012833`
- `USER32!SendMessageW` at `0x1800127db`
- `USER32!SendMessageW` at `0x180012833`
- `USER32!SetWindowTextW` at `0x1800127ec`
- `USER32!SetWindowTextW` at `0x1800127ec`

## pseudocode

```c
__int64 __fastcall CDeviceSettingsDialog::SetSelectedPrinterNameFromServer(CDeviceSettingsDialog *this, HWND a2)
{
  DWORD LastError; // eax
  DWORD v5; // ebx
  WCHAR *v7; // rbx
  __int64 v8; // rax
  unsigned int v9; // ebp
  __int64 v10; // r14
  unsigned int v11; // edi
  LPARAM v12; // r9
  int v13; // [rsp+70h] [rbp+8h] BYREF
  LPCWSTR lpString2; // [rsp+80h] [rbp+18h] BYREF

  lpString2 = 0;
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  if ( (unsigned int)FaxGetExtensionDataW(
                       *((_QWORD *)this + 7),
                       *(unsigned int *)(*((_QWORD *)this + 6) + 4LL),
                       L"{aec1b37c-9af2-11d0-abf7-00c04fd91a4e}",
                       &lpString2,
                       &v13) )
  {
    v7 = (WCHAR *)lpString2;
    if ( lpString2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( lpString2[v8] );
      if ( v8 )
      {
        v9 = *((_DWORD *)this + 18);
        v10 = *((_QWORD *)this + 8);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids);
        }
        if ( !v10 || !v9 || !v7 )
          goto LABEL_25;
        v11 = 0;
        while ( lstrcmpiW(*(LPCWSTR *)(v10 + 16LL * v11 + 8), v7) )
        {
          if ( ++v11 >= v9 )
            goto LABEL_25;
        }
        v12 = *(_QWORD *)(v10 + 16LL * v11);
        if ( v12 )
        {
          SendMessageW(a2, 0x14Du, 0xFFFFFFFFFFFFFFFFuLL, v12);
        }
        else
        {
LABEL_25:
          SendMessageW(a2, 0x14Eu, 0xFFFFFFFFFFFFFFFFuLL, 0);
          SetWindowTextW(a2, lpString2);
        }
        v7 = (WCHAR *)lpString2;
      }
      if ( v7 )
        FaxFreeBuffer(v7);
    }
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180012670  mov     rax, rsp
0x180012673  mov     [rax+10h], rbx
0x180012677  push    rbp
0x180012678  push    rsi
0x180012679  push    rdi
0x18001267a  push    r12
0x18001267c  push    r13
0x18001267e  push    r14
0x180012680  push    r15
0x180012682  sub     rsp, 30h
0x180012686  xor     r12d, r12d
0x180012689  mov     r15, rdx
0x18001268c  mov     [rax+18h], r12
0x180012690  mov     r14, rcx
0x180012693  mov     [rax+8], r12d
0x180012697  mov     rcx, cs:WPP_GLOBAL_Control
0x18001269e  lea     rsi, WPP_GLOBAL_Control
0x1800126a5  mov     edi, 100h
0x1800126aa  cmp     rcx, rsi
0x1800126ad  jz      short loc_1800126CF
0x1800126af  test    [rcx+1Ch], edi
0x1800126b2  jz      short loc_1800126CF
0x1800126b4  cmp     byte ptr [rcx+19h], 5
0x1800126b8  jb      short loc_1800126CF
0x1800126ba  mov     rcx, [rcx+10h]
0x1800126be  lea     edx, [r12+2Ah]
0x1800126c3  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800126ca  call    WPP_SF_
0x1800126cf  mov     rdx, [r14+30h]
0x1800126d3  lea     rax, [rsp+68h+arg_0]
0x1800126d8  mov     rcx, [r14+38h]
0x1800126dc  lea     r9, [rsp+68h+lpString2]
0x1800126e4  lea     r8, RoutingGuid; "{aec1b37c-9af2-11d0-abf7-00c04fd91a4e}"
0x1800126eb  mov     [rsp+68h+var_48], rax
0x1800126f0  mov     edx, [rdx+4]
0x1800126f3  call    cs:__imp_FaxGetExtensionDataW
0x1800126f9  test    eax, eax
0x1800126fb  jnz     short loc_18001273B
0x1800126fd  call    cs:__imp_GetLastError
0x180012703  mov     ebx, eax
0x180012705  mov     rcx, cs:WPP_GLOBAL_Control
0x18001270c  cmp     rcx, rsi
0x18001270f  jz      short loc_180012734
0x180012711  test    [rcx+1Ch], edi
0x180012714  jz      short loc_180012734
0x180012716  cmp     byte ptr [rcx+19h], 3
0x18001271a  jb      short loc_180012734
0x18001271c  mov     rcx, [rcx+10h]
0x180012720  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180012727  mov     edx, 2Bh ; '+'
0x18001272c  mov     r9d, eax
0x18001272f  call    WPP_SF_d
0x180012734  mov     eax, ebx
0x180012736  jmp     loc_18001280A
0x18001273b  mov     rbx, [rsp+68h+lpString2]
0x180012743  test    rbx, rbx
0x180012746  jz      loc_180012808
0x18001274c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180012750  mov     rax, r13
0x180012753  inc     rax
0x180012756  cmp     [rbx+rax*2], r12w
0x18001275b  jnz     short loc_180012753
0x18001275d  test    rax, rax
0x180012760  jz      loc_1800127FA
0x180012766  mov     ebp, [r14+48h]
0x18001276a  mov     r14, [r14+40h]
0x18001276e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012775  cmp     rcx, rsi
0x180012778  jz      short loc_18001279B
0x18001277a  test    byte ptr [rcx+1Ch], 2
0x18001277e  jz      short loc_18001279B
0x180012780  cmp     byte ptr [rcx+19h], 5
0x180012784  jb      short loc_18001279B
0x180012786  mov     rcx, [rcx+10h]
0x18001278a  lea     r8, WPP_157c8f22104f3bf76480eff3c0994dfa_Traceguids
0x180012791  mov     edx, 29h ; ')'
0x180012796  call    WPP_SF_
0x18001279b  test    r14, r14
0x18001279e  jz      short loc_1800127CD
0x1800127a0  test    ebp, ebp
0x1800127a2  jz      short loc_1800127CD
0x1800127a4  test    rbx, rbx
0x1800127a7  jz      short loc_1800127CD
0x1800127a9  mov     edi, r12d
0x1800127ac  test    ebp, ebp
0x1800127ae  jz      short loc_1800127CD
0x1800127b0  mov     esi, edi
0x1800127b2  mov     rdx, rbx; lpString2
0x1800127b5  add     rsi, rsi
0x1800127b8  mov     rcx, [r14+rsi*8+8]; lpString1
0x1800127bd  call    cs:__imp_lstrcmpiW
0x1800127c3  test    eax, eax
0x1800127c5  jz      short loc_18001281F
0x1800127c7  inc     edi
0x1800127c9  cmp     edi, ebp
0x1800127cb  jb      short loc_1800127B0
0x1800127cd  xor     r9d, r9d; lParam
0x1800127d0  mov     r8, r13; wParam
0x1800127d3  mov     edx, 14Eh; Msg
0x1800127d8  mov     rcx, r15; hWnd
0x1800127db  call    cs:__imp_SendMessageW
0x1800127e1  mov     rdx, [rsp+68h+lpString2]; lpString
0x1800127e9  mov     rcx, r15; hWnd
0x1800127ec  call    cs:__imp_SetWindowTextW
0x1800127f2  mov     rbx, [rsp+68h+lpString2]
0x1800127fa  test    rbx, rbx
0x1800127fd  jz      short loc_180012808
0x1800127ff  mov     rcx, rbx; Buffer
0x180012802  call    cs:__imp_FaxFreeBuffer
0x180012808  xor     eax, eax
0x18001280a  mov     rbx, [rsp+68h+arg_8]
0x18001280f  add     rsp, 30h
0x180012813  pop     r15
0x180012815  pop     r14
0x180012817  pop     r13
0x180012819  pop     r12
0x18001281b  pop     rdi
0x18001281c  pop     rsi
0x18001281d  pop     rbp
0x18001281e  retn
0x18001281f  mov     r9, [r14+rsi*8]; lParam
0x180012823  test    r9, r9
0x180012826  jz      short loc_1800127CD
0x180012828  mov     r8, r13; wParam
0x18001282b  mov     edx, 14Dh; Msg
0x180012830  mov     rcx, r15; hWnd
0x180012833  call    cs:__imp_SendMessageW
0x180012839  jmp     short loc_1800127F2
```
