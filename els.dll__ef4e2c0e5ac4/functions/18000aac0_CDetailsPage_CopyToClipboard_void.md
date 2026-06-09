# CDetailsPage::_CopyToClipboard(void)

- ea: `0x18000aac0`
- end: `0x18000ae22`
- name: `?_CopyToClipboard@CDetailsPage@@AEAAXXZ`
- size: `866`
- prototype: `void __fastcall(CDetailsPage *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18000b0d0`

## callees

- `0x180001910`
- `0x18000513c`
- `0x180007014`
- `0x180009dcc`
- `0x18000aac0`
- `0x18000d814`
- `0x180019a28`
- `0x180019ae4`
- `0x180019b68`
- `0x180019be8`
- `0x180019c40`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000abfd`
- `msvcrt!swprintf_s` at `0x18000abfd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae04`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ae04`
- `KERNEL32!LocalFree` at `0x18000ad14`
- `KERNEL32!LocalFree` at `0x18000ad14`
- `KERNEL32!GlobalFree` at `0x18000adf9`
- `KERNEL32!GlobalFree` at `0x18000adf9`
- `KERNEL32!GlobalAlloc` at `0x18000ad6c`
- `KERNEL32!GlobalAlloc` at `0x18000ad6c`
- `KERNEL32!GlobalLock` at `0x18000ad78`
- `KERNEL32!GlobalLock` at `0x18000ad78`
- `KERNEL32!GlobalUnlock` at `0x18000adb8`
- `KERNEL32!GlobalUnlock` at `0x18000adb8`
- `USER32!OpenClipboard` at `0x18000ab16`
- `USER32!OpenClipboard` at `0x18000ab16`
- `USER32!EmptyClipboard` at `0x18000ab26`
- `USER32!EmptyClipboard` at `0x18000ab26`
- `USER32!IsDlgButtonChecked` at `0x18000ad2d`
- `USER32!IsDlgButtonChecked` at `0x18000ad2d`
- `USER32!CloseClipboard` at `0x18000adeb`
- `USER32!CloseClipboard` at `0x18000adeb`
- `USER32!SetClipboardData` at `0x18000adc6`
- `USER32!SetClipboardData` at `0x18000adc6`

## pseudocode

```c
void __fastcall CDetailsPage::_CopyToClipboard(CDetailsPage *this)
{
  __int64 v2; // rcx
  HGLOBAL v3; // rdi
  unsigned __int16 *TypeStr; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  const unsigned __int16 *DescriptionStr; // rax
  unsigned __int16 *v8; // rdi
  __int64 v9; // r8
  unsigned __int16 *v10; // rax
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r8
  HANDLE v13; // rbx
  __int64 v14; // rdx
  HGLOBAL v15; // rdx
  struct _EVENTLOGRECORD *v16; // [rsp+30h] [rbp-D0h] BYREF
  struct CLogInfo *v17; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v20; // [rsp+58h] [rbp-A8h]
  wchar_t Buffer[80]; // [rsp+60h] [rbp-A0h] BYREF

  v16 = 0;
  v2 = *((_QWORD *)this + 6);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, struct _EVENTLOGRECORD **))(*(_QWORD *)v2 + 48LL))(v2, &v16);
    if ( v16 )
    {
      if ( OpenClipboard(*((HWND *)this + 2)) )
      {
        v3 = 0;
        if ( EmptyClipboard() )
        {
          std::wstring::wstring(v18);
          memset_0(Buffer, 0, sizeof(Buffer));
          TypeStr = GetTypeStr(v16->EventType);
          AppendToClipboardString(v18, 313, TypeStr, 0);
          AppendToClipboardString(v18, 314, &v16[1], 0);
          v17 = 0;
          v5 = *((_QWORD *)this + 6);
          if ( v5 )
          {
            (*(void (__fastcall **)(__int64, struct CLogInfo **))(*(_QWORD *)v5 + 40LL))(v5, &v17);
            if ( v17 )
              GetCategoryStr(v17, v16, Buffer, 0x50u);
          }
          AppendToClipboardString(v18, 315, Buffer, 0);
          swprintf_s(Buffer, 0x50u, L"%u", LOWORD(v16->EventID));
          AppendToClipboardString(v18, 316, Buffer, 0);
          GetDateStr(v16->TimeGenerated, Buffer, 0x50u);
          AppendToClipboardString(v18, 317, Buffer, 0);
          GetTimeStr(v16->TimeGenerated, Buffer, 0x50u);
          AppendToClipboardString(v18, 318, Buffer, 0);
          GetUserStr(v16, Buffer, 0x50u, 1);
          AppendToClipboardString(v18, 319, Buffer, 0);
          v6 = -1;
          do
            ++v6;
          while ( *((_WORD *)&v16[1].Length + v6) );
          AppendToClipboardString(v18, 320, (char *)&v16[1].Length + 2 * v6 + 2, 0);
          if ( v17 )
          {
            DescriptionStr = GetDescriptionStr((__int64)v17, v16, (__int64)this + 112, 1, 0);
            v8 = (unsigned __int16 *)DescriptionStr;
            if ( DescriptionStr )
            {
              AppendToClipboardString(v18, 321, DescriptionStr, 1);
              LocalFree(v8);
            }
          }
          if ( v16->DataLength )
          {
            v9 = *(_QWORD *)((char *)this + (IsDlgButtonChecked(*((HWND *)this + 2), 131) != 0 ? 0x10 : 0) + 56);
            if ( v9 )
              AppendToClipboardString(v18, 322, v9, 1);
          }
          v3 = GlobalAlloc(0x2002u, 2 * v19 + 2);
          v10 = (unsigned __int16 *)GlobalLock(v3);
          if ( v10 )
          {
            v12 = (const unsigned __int16 *)v18;
            if ( v20 >= 8 )
              v12 = v18[0];
            StringCchCopyW(v10, v19 + 1, v12);
            GlobalUnlock(v3);
            v13 = SetClipboardData(0xDu, v3);
            LOBYTE(v14) = 1;
            std::wstring::_Tidy(v18, v14, 0);
            v15 = 0;
            if ( !v13 )
              v15 = v3;
            v3 = v15;
          }
          else
          {
            LOBYTE(v11) = 1;
            std::wstring::_Tidy(v18, v11, 0);
          }
        }
        CloseClipboard();
        if ( v3 )
          GlobalFree(v3);
      }
    }
  }
  operator delete(v16);
}

```

## disassembly

```asm
0x18000aac0  push    rbp
0x18000aac2  push    rbx
0x18000aac3  push    rsi
0x18000aac4  push    rdi
0x18000aac5  lea     rbp, [rsp-18h]
0x18000aaca  sub     rsp, 118h
0x18000aad1  mov     rax, cs:__security_cookie
0x18000aad8  xor     rax, rsp
0x18000aadb  mov     [rbp+30h+var_30], rax
0x18000aadf  mov     rbx, rcx
0x18000aae2  xor     esi, esi
0x18000aae4  mov     [rsp+130h+var_100], rsi
0x18000aae9  mov     rcx, [rcx+30h]
0x18000aaed  test    rcx, rcx
0x18000aaf0  jz      loc_18000ADFF
0x18000aaf6  mov     rax, [rcx]
0x18000aaf9  lea     rdx, [rsp+130h+var_100]
0x18000aafe  mov     rax, [rax+30h]
0x18000ab02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab07  cmp     [rsp+130h+var_100], rsi
0x18000ab0c  jz      loc_18000ADFF
0x18000ab12  mov     rcx, [rbx+10h]; hWndNewOwner
0x18000ab16  call    cs:__imp_OpenClipboard
0x18000ab1c  test    eax, eax
0x18000ab1e  jz      loc_18000ADFF
0x18000ab24  mov     edi, esi
0x18000ab26  call    cs:__imp_EmptyClipboard
0x18000ab2c  test    eax, eax
0x18000ab2e  jz      loc_18000ADEB
0x18000ab34  lea     rcx, [rsp+130h+var_F0]
0x18000ab39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000ab3e  nop
0x18000ab3f  xor     edx, edx; Val
0x18000ab41  mov     r8d, 0A0h; Size
0x18000ab47  lea     rcx, [rsp+130h+Buffer]; void *
0x18000ab4c  call    memset_0
0x18000ab51  mov     rcx, [rsp+130h+var_100]
0x18000ab56  movzx   ecx, word ptr [rcx+18h]; unsigned __int16
0x18000ab5a  call    ?GetTypeStr@@YAPEAGG@Z; GetTypeStr(ushort)
0x18000ab5f  mov     r8, rax
0x18000ab62  xor     r9d, r9d
0x18000ab65  mov     edx, 139h
0x18000ab6a  lea     rcx, [rsp+130h+var_F0]
0x18000ab6f  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ab74  mov     r8, [rsp+130h+var_100]
0x18000ab79  add     r8, 38h ; '8'
0x18000ab7d  xor     r9d, r9d
0x18000ab80  mov     edx, 13Ah
0x18000ab85  lea     rcx, [rsp+130h+var_F0]
0x18000ab8a  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ab8f  mov     [rsp+130h+var_F8], rsi
0x18000ab94  mov     rcx, [rbx+30h]
0x18000ab98  lea     edi, [rsi+50h]
0x18000ab9b  test    rcx, rcx
0x18000ab9e  jz      short loc_18000ABCD
0x18000aba0  mov     rax, [rcx]
0x18000aba3  lea     rdx, [rsp+130h+var_F8]
0x18000aba8  mov     rax, [rax+28h]
0x18000abac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb1  mov     rcx, [rsp+130h+var_F8]; struct CLogInfo *
0x18000abb6  test    rcx, rcx
0x18000abb9  jz      short loc_18000ABCD
0x18000abbb  mov     r9d, edi; unsigned int
0x18000abbe  lea     r8, [rsp+130h+Buffer]; unsigned __int16 *
0x18000abc3  mov     rdx, [rsp+130h+var_100]; struct _EVENTLOGRECORD *
0x18000abc8  call    ?GetCategoryStr@@YAPEAGPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@PEAGK@Z; GetCategoryStr(CLogInfo *,_EVENTLOGRECORD *,ushort *,ulong)
0x18000abcd  xor     r9d, r9d
0x18000abd0  lea     r8, [rsp+130h+Buffer]
0x18000abd5  mov     edx, 13Bh
0x18000abda  lea     rcx, [rsp+130h+var_F0]
0x18000abdf  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000abe4  mov     rax, [rsp+130h+var_100]
0x18000abe9  movzx   r9d, word ptr [rax+14h]
0x18000abee  lea     r8, aU_0; "%u"
0x18000abf5  mov     rdx, rdi; BufferCount
0x18000abf8  lea     rcx, [rsp+130h+Buffer]; Buffer
0x18000abfd  call    cs:__imp_swprintf_s
0x18000ac03  xor     r9d, r9d
0x18000ac06  lea     r8, [rsp+130h+Buffer]
0x18000ac0b  mov     edx, 13Ch
0x18000ac10  lea     rcx, [rsp+130h+var_F0]
0x18000ac15  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ac1a  mov     r8d, edi; unsigned int
0x18000ac1d  lea     rdx, [rsp+130h+Buffer]; unsigned __int16 *
0x18000ac22  mov     rcx, [rsp+130h+var_100]
0x18000ac27  mov     ecx, [rcx+0Ch]; unsigned int
0x18000ac2a  call    ?GetDateStr@@YAPEAGKPEAGK@Z; GetDateStr(ulong,ushort *,ulong)
0x18000ac2f  xor     r9d, r9d
0x18000ac32  lea     r8, [rsp+130h+Buffer]
0x18000ac37  mov     edx, 13Dh
0x18000ac3c  lea     rcx, [rsp+130h+var_F0]
0x18000ac41  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ac46  mov     r8d, edi; unsigned int
0x18000ac49  lea     rdx, [rsp+130h+Buffer]; unsigned __int16 *
0x18000ac4e  mov     rcx, [rsp+130h+var_100]
0x18000ac53  mov     ecx, [rcx+0Ch]; unsigned int
0x18000ac56  call    ?GetTimeStr@@YAPEAGKPEAGK@Z; GetTimeStr(ulong,ushort *,ulong)
0x18000ac5b  xor     r9d, r9d
0x18000ac5e  lea     r8, [rsp+130h+Buffer]
0x18000ac63  mov     edx, 13Eh
0x18000ac68  lea     rcx, [rsp+130h+var_F0]
0x18000ac6d  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ac72  mov     r9d, 1; int
0x18000ac78  mov     r8d, edi; unsigned int
0x18000ac7b  lea     rdx, [rsp+130h+Buffer]; unsigned __int16 *
0x18000ac80  mov     rcx, [rsp+130h+var_100]; struct _EVENTLOGRECORD *
0x18000ac85  call    ?GetUserStr@@YAPEAGPEAU_EVENTLOGRECORD@@PEAGKH@Z; GetUserStr(_EVENTLOGRECORD *,ushort *,ulong,int)
0x18000ac8a  xor     r9d, r9d
0x18000ac8d  lea     r8, [rsp+130h+Buffer]
0x18000ac92  mov     edx, 13Fh
0x18000ac97  lea     rcx, [rsp+130h+var_F0]
0x18000ac9c  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000aca1  mov     rcx, [rsp+130h+var_100]
0x18000aca6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000acaa  inc     rax
0x18000acad  cmp     [rcx+rax*2+38h], si
0x18000acb2  jnz     short loc_18000ACAA
0x18000acb4  add     rcx, 3Ah ; ':'
0x18000acb8  lea     r8, [rcx+rax*2]
0x18000acbc  xor     r9d, r9d
0x18000acbf  mov     edx, 140h
0x18000acc4  lea     rcx, [rsp+130h+var_F0]
0x18000acc9  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000acce  mov     rcx, [rsp+130h+var_F8]
0x18000acd3  test    rcx, rcx
0x18000acd6  jz      short loc_18000AD1A
0x18000acd8  lea     r8, [rbx+70h]
0x18000acdc  mov     [rsp+130h+var_110], rsi
0x18000ace1  mov     r9d, 1
0x18000ace7  mov     rdx, [rsp+130h+var_100]
0x18000acec  call    ?GetDescriptionStr@@YAPEAGPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HPEAPEAG@Z; GetDescriptionStr(CLogInfo *,_EVENTLOGRECORD *,std::wstring *,int,ushort * *)
0x18000acf1  mov     rdi, rax
0x18000acf4  test    rax, rax
0x18000acf7  jz      short loc_18000AD1A
0x18000acf9  mov     r9d, 1
0x18000acff  mov     r8, rax
0x18000ad02  mov     edx, 141h
0x18000ad07  lea     rcx, [rsp+130h+var_F0]
0x18000ad0c  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ad11  mov     rcx, rdi; hMem
0x18000ad14  call    cs:__imp_LocalFree
0x18000ad1a  mov     rax, [rsp+130h+var_100]
0x18000ad1f  cmp     [rax+30h], esi
0x18000ad22  jz      short loc_18000AD5A
0x18000ad24  mov     edx, 83h; nIDButton
0x18000ad29  mov     rcx, [rbx+10h]; hDlg
0x18000ad2d  call    cs:__imp_IsDlgButtonChecked
0x18000ad33  neg     eax
0x18000ad35  sbb     rcx, rcx
0x18000ad38  and     ecx, 10h
0x18000ad3b  mov     r8, [rcx+rbx+38h]
0x18000ad40  test    r8, r8
0x18000ad43  jz      short loc_18000AD5A
0x18000ad45  mov     edx, 142h
0x18000ad4a  mov     r9d, 1
0x18000ad50  lea     rcx, [rsp+130h+var_F0]
0x18000ad55  call    ?AppendToClipboardString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBGH@Z; AppendToClipboardString(std::wstring &,ulong,ushort const *,int)
0x18000ad5a  mov     rdx, [rsp+130h+var_E0]
0x18000ad5f  lea     rdx, ds:2[rdx*2]; dwBytes
0x18000ad67  mov     ecx, 2002h; uFlags
0x18000ad6c  call    cs:__imp_GlobalAlloc
0x18000ad72  mov     rdi, rax
0x18000ad75  mov     rcx, rax; hMem
0x18000ad78  call    cs:__imp_GlobalLock
0x18000ad7e  test    rax, rax
0x18000ad81  jnz     short loc_18000AD94
0x18000ad83  xor     r8d, r8d
0x18000ad86  mov     dl, 1
0x18000ad88  lea     rcx, [rsp+130h+var_F0]
0x18000ad8d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ad92  jmp     short loc_18000ADEB
0x18000ad94  lea     r8, [rsp+130h+var_F0]
0x18000ad99  cmp     [rsp+130h+var_D8], 8
0x18000ad9f  cmovnb  r8, [rsp+130h+var_F0]; unsigned __int16 *
0x18000ada5  mov     rdx, [rsp+130h+var_E0]
0x18000adaa  inc     rdx; unsigned __int64
0x18000adad  mov     rcx, rax; unsigned __int16 *
0x18000adb0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000adb5  mov     rcx, rdi; hMem
0x18000adb8  call    cs:__imp_GlobalUnlock
0x18000adbe  mov     rdx, rdi; hMem
0x18000adc1  mov     ecx, 0Dh; uFormat
0x18000adc6  call    cs:__imp_SetClipboardData
0x18000adcc  mov     rbx, rax
0x18000adcf  xor     r8d, r8d
0x18000add2  mov     dl, 1
0x18000add4  lea     rcx, [rsp+130h+var_F0]
0x18000add9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000adde  mov     rdx, rsi
0x18000ade1  test    rbx, rbx
0x18000ade4  cmovz   rdx, rdi
0x18000ade8  mov     rdi, rdx
0x18000adeb  call    cs:__imp_CloseClipboard
0x18000adf1  test    rdi, rdi
0x18000adf4  jz      short loc_18000ADFF
0x18000adf6  mov     rcx, rdi; hMem
0x18000adf9  call    cs:__imp_GlobalFree
0x18000adff  mov     rcx, [rsp+130h+var_100]
0x18000ae04  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ae0a  mov     rcx, [rbp+30h+var_30]
0x18000ae0e  xor     rcx, rsp; StackCookie
0x18000ae11  call    __security_check_cookie
0x18000ae16  add     rsp, 118h
0x18000ae1d  pop     rdi
0x18000ae1e  pop     rsi
0x18000ae1f  pop     rbx
0x18000ae20  pop     rbp
0x18000ae21  retn
```
