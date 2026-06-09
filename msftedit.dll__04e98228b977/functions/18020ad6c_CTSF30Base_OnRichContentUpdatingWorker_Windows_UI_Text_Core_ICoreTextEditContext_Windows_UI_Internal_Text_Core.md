# CTSF30Base::OnRichContentUpdatingWorker(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *)

- ea: `0x18020ad6c`
- end: `0x18020b088`
- name: `?OnRichContentUpdatingWorker@CTSF30Base@@QEAAJPEAUICoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextRichContentUpdatingEventArgs@34Internal@56@@Z`
- size: `796`
- prototype: `__int64 __fastcall(CTSF30Base *__hidden this, struct Windows::UI::Text::Core::ICoreTextEditContext *, struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18020a560`

## callees

- `0x180043e7c`
- `0x18009abd0`
- `0x1800eba94`
- `0x180100ff8`
- `0x18010d6a8`
- `0x18020ad6c`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020aee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020af1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020aee4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020af1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020ae70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020ae9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020afc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020afd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020ae70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020ae9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020afc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020afd6`

## pseudocode

```c
__int64 __fastcall CTSF30Base::OnRichContentUpdatingWorker(
        CTSF30Base *this,
        struct Windows::UI::Text::Core::ICoreTextEditContext *a2,
        struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *a3)
{
  __int64 v4; // r8
  __int64 result; // rax
  __int64 (__fastcall *v7)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *); // rax
  int v8; // eax
  int v9; // esi
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  void (__fastcall *v14)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  void (__fastcall *v15)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *); // rbx
  unsigned __int16 *v16; // rbx
  unsigned __int16 *v17; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v26; // [rsp+38h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v29; // [rsp+50h] [rbp-30h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h] BYREF
  __int128 v31; // [rsp+68h] [rbp-18h]
  unsigned __int16 *v32; // [rsp+78h] [rbp-8h]
  int v33; // [rsp+C0h] [rbp+40h] BYREF
  struct Windows::UI::Text::Core::ICoreTextEditContext *length; // [rsp+C8h] [rbp+48h] BYREF
  HSTRING v35; // [rsp+D8h] [rbp+58h] BYREF

  length = a2;
  *((_BYTE *)this + 112) = 1;
  v4 = *(_QWORD *)a3;
  if ( (*(_BYTE *)(*((_QWORD *)this + 13) + 176LL) & 4) != 0 )
  {
    result = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(v4 + 104))(
               a3,
               1);
  }
  else
  {
    v7 = *(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64 *))(v4 + 48);
    v27 = 0;
    v8 = v7(a3, &v27);
    v33 = 0;
    v9 = v8;
    if ( v8 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, int *))(*(_QWORD *)a3 + 88LL))(
             a3,
             &v33);
      if ( v9 >= 0 && v33 != 4 )
      {
        v10 = *(_QWORD *)(*((_QWORD *)this + 13) + 256LL);
        if ( v10 )
          v11 = *(_DWORD *)(v10 + 236);
        else
          v11 = 0;
        if ( (v11 & v33) == 0 || (_DWORD)v27 == HIDWORD(v27) )
        {
          v9 = -2147467259;
        }
        else
        {
          v12 = *((_QWORD *)this + 13) + 16LL;
          v26 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 424LL))(
                 v12,
                 v27,
                 HIDWORD(v27),
                 &v26);
          if ( v9 >= 0 )
          {
            v13 = *(_QWORD *)a3;
            string = 0;
            v35 = 0;
            v14 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(v13 + 72);
            WindowsDeleteString(0);
            v35 = 0;
            v14(a3, &v35);
            v15 = *(void (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
            WindowsDeleteString(0);
            string = 0;
            v15(a3, &string);
            v28 = 0;
            LODWORD(length) = 0;
            v16 = 0;
            v32 = 0;
            v30 = 0;
            v17 = 0;
            v29 = 0;
            v31 = 0;
            StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
            if ( !(_DWORD)length
              || (v19 = Resp::BStrHolder::HrCopyRgwch((Resp::BStrHolder *)&v28, StringRawBuffer, (unsigned int)length),
                  v17 = v28,
                  v9 = v19,
                  v19 >= 0) )
            {
              v20 = WindowsGetStringRawBuffer(v35, (UINT32 *)&length);
              if ( !(_DWORD)length
                || (v21 = Resp::BStrHolder::HrCopyRgwch((Resp::BStrHolder *)&v29, v20, (unsigned int)length),
                    v16 = v29,
                    v9 = v21,
                    v21 >= 0) )
              {
                (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 112LL))(v26, (char *)&v30 + 4);
                (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 128LL))(v26, (char *)&v30 + 8);
                v22 = *((_QWORD *)this + 13);
                HIDWORD(v30) = v33;
                *((_QWORD *)&v31 + 1) = v17;
                v32 = v16;
                v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v22 + 24LL))(
                       v22,
                       1390,
                       0,
                       &v30,
                       0);
              }
              if ( v16 )
                CW32System::SysFreeString(v16);
            }
            if ( v17 )
              CW32System::SysFreeString(v17);
            WindowsDeleteString(v35);
            v35 = 0;
            WindowsDeleteString(string);
          }
          Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v26);
        }
      }
    }
    LODWORD(string) = 0;
    LODWORD(length) = 0x3FFFFFFF;
    LODWORD(v35) = 0;
    CTextInputDriverNotifyChanges::GetChanges(
      (CTSF30Base *)((char *)this + 152),
      (int *)&length,
      (int *)&string,
      (int *)&v35);
    if ( v9 < 0 || (_DWORD)length == 0x3FFFFFFF )
    {
      v23 = (*(__int64 (__fastcall **)(struct Windows::UI::Internal::Text::Core::ICoreTextRichContentUpdatingEventArgs *, __int64))(*(_QWORD *)a3 + 104LL))(
              a3,
              1);
    }
    else
    {
      v23 = 0;
      CTSF30Base::SendTextChangedNotification(
        this,
        (int)length,
        (_DWORD)string - (_DWORD)length,
        (_DWORD)v35 - (_DWORD)length);
    }
    v24 = *((_QWORD *)this + 13);
    if ( (*(_BYTE *)(v24 + 184) & 0x10) == 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(v24 + 16) + 168LL))(v24 + 16);
    result = v23;
  }
  *((_BYTE *)this + 112) = 0;
  return result;
}

```

## disassembly

```asm
0x18020ad6c  mov     [rsp-38h+length], rdx
0x18020ad71  push    rbp
0x18020ad72  push    rbx
0x18020ad73  push    rsi
0x18020ad74  push    rdi
0x18020ad75  push    r12
0x18020ad77  push    r14
0x18020ad79  push    r15
0x18020ad7b  mov     rbp, rsp
0x18020ad7e  sub     rsp, 80h
0x18020ad85  mov     byte ptr [rcx+70h], 1
0x18020ad89  mov     r15, r8
0x18020ad8c  mov     rax, [rcx+68h]
0x18020ad90  xor     r12d, r12d
0x18020ad93  mov     r8, [r8]
0x18020ad96  mov     r14, rcx
0x18020ad99  mov     rcx, r15
0x18020ad9c  test    byte ptr [rax+0B0h], 4
0x18020ada3  jz      short loc_18020ADB8
0x18020ada5  mov     rax, [r8+68h]
0x18020ada9  lea     edx, [r12+1]
0x18020adae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020adb3  jmp     loc_18020B071
0x18020adb8  mov     rax, [r8+30h]
0x18020adbc  lea     rdx, [rbp+var_40]
0x18020adc0  mov     [rbp+var_40], r12
0x18020adc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020adc9  mov     [rbp+arg_0], r12d
0x18020adcd  mov     esi, eax
0x18020adcf  test    eax, eax
0x18020add1  js      loc_18020AFEB
0x18020add7  mov     rax, [r15]
0x18020adda  lea     rdx, [rbp+arg_0]
0x18020adde  mov     rcx, r15
0x18020ade1  mov     rax, [rax+58h]
0x18020ade5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020adea  mov     esi, eax
0x18020adec  test    eax, eax
0x18020adee  js      loc_18020AFEB
0x18020adf4  mov     ecx, [rbp+arg_0]
0x18020adf7  cmp     ecx, 4
0x18020adfa  jz      loc_18020AFEB
0x18020ae00  mov     rax, [r14+68h]
0x18020ae04  mov     rax, [rax+100h]
0x18020ae0b  test    rax, rax
0x18020ae0e  jz      short loc_18020AE18
0x18020ae10  mov     eax, [rax+0ECh]
0x18020ae16  jmp     short loc_18020AE1B
0x18020ae18  mov     eax, r12d
0x18020ae1b  test    ecx, eax
0x18020ae1d  jnz     short loc_18020AE29
0x18020ae1f  mov     esi, 80004005h
0x18020ae24  jmp     loc_18020AFEB
0x18020ae29  mov     rdx, [rbp+var_40]
0x18020ae2d  mov     r8d, dword ptr [rbp+var_40+4]
0x18020ae31  cmp     edx, r8d
0x18020ae34  jz      short loc_18020AE1F
0x18020ae36  mov     rcx, [r14+68h]
0x18020ae3a  lea     r9, [rbp+var_48]
0x18020ae3e  add     rcx, 10h
0x18020ae42  mov     [rbp+var_48], r12
0x18020ae46  mov     rax, [rcx]
0x18020ae49  mov     rax, [rax+1A8h]
0x18020ae50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020ae55  mov     esi, eax
0x18020ae57  test    eax, eax
0x18020ae59  js      loc_18020AFE2
0x18020ae5f  mov     rax, [r15]
0x18020ae62  xor     ecx, ecx; string
0x18020ae64  mov     [rbp+string], r12
0x18020ae68  mov     [rbp+arg_18], r12
0x18020ae6c  mov     rbx, [rax+48h]
0x18020ae70  call    cs:__imp_WindowsDeleteString
0x18020ae77  nop     dword ptr [rax+rax+00h]
0x18020ae7c  lea     rdx, [rbp+arg_18]
0x18020ae80  mov     [rbp+arg_18], r12
0x18020ae84  mov     rcx, r15
0x18020ae87  mov     rax, rbx
0x18020ae8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020ae8f  mov     rax, [r15]
0x18020ae92  mov     rcx, [rbp+string]; string
0x18020ae96  mov     rbx, [rax+38h]
0x18020ae9a  call    cs:__imp_WindowsDeleteString
0x18020aea1  nop     dword ptr [rax+rax+00h]
0x18020aea6  lea     rdx, [rbp+string]
0x18020aeaa  mov     [rbp+string], r12
0x18020aeae  mov     rcx, r15
0x18020aeb1  mov     rax, rbx
0x18020aeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020aeb9  mov     rcx, [rbp+string]; string
0x18020aebd  lea     rdx, [rbp+length]; length
0x18020aec1  xorps   xmm0, xmm0
0x18020aec4  mov     [rbp+var_38], r12
0x18020aec8  xor     eax, eax
0x18020aeca  mov     dword ptr [rbp+length], r12d
0x18020aece  mov     rbx, r12
0x18020aed1  mov     [rbp+var_8], rax
0x18020aed5  movups  [rbp+var_28], xmm0
0x18020aed9  mov     rdi, r12
0x18020aedc  mov     [rbp+var_30], rbx
0x18020aee0  movups  [rbp+var_18], xmm0
0x18020aee4  call    cs:__imp_WindowsGetStringRawBuffer
0x18020aeeb  nop     dword ptr [rax+rax+00h]
0x18020aef0  mov     ecx, dword ptr [rbp+length]
0x18020aef3  test    ecx, ecx
0x18020aef5  jz      short loc_18020AF14
0x18020aef7  mov     r8d, ecx; unsigned __int64
0x18020aefa  mov     rdx, rax; unsigned __int16 *
0x18020aefd  lea     rcx, [rbp+var_38]; this
0x18020af01  call    ?HrCopyRgwch@BStrHolder@Resp@@QEAAJPEBG_K@Z; Resp::BStrHolder::HrCopyRgwch(ushort const *,unsigned __int64)
0x18020af06  mov     rdi, [rbp+var_38]
0x18020af0a  mov     esi, eax
0x18020af0c  test    eax, eax
0x18020af0e  js      loc_18020AFB1
0x18020af14  mov     rcx, [rbp+arg_18]; string
0x18020af18  lea     rdx, [rbp+length]; length
0x18020af1c  call    cs:__imp_WindowsGetStringRawBuffer
0x18020af23  nop     dword ptr [rax+rax+00h]
0x18020af28  mov     ecx, dword ptr [rbp+length]
0x18020af2b  test    ecx, ecx
0x18020af2d  jz      short loc_18020AF48
0x18020af2f  mov     r8d, ecx; unsigned __int64
0x18020af32  mov     rdx, rax; unsigned __int16 *
0x18020af35  lea     rcx, [rbp+var_30]; this
0x18020af39  call    ?HrCopyRgwch@BStrHolder@Resp@@QEAAJPEBG_K@Z; Resp::BStrHolder::HrCopyRgwch(ushort const *,unsigned __int64)
0x18020af3e  mov     rbx, [rbp+var_30]
0x18020af42  mov     esi, eax
0x18020af44  test    eax, eax
0x18020af46  js      short loc_18020AFA4
0x18020af48  mov     rcx, [rbp+var_48]
0x18020af4c  lea     rdx, [rbp+var_28+4]
0x18020af50  mov     rax, [rcx]
0x18020af53  mov     rax, [rax+70h]
0x18020af57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020af5c  mov     rcx, [rbp+var_48]
0x18020af60  lea     rdx, [rbp+var_28+8]
0x18020af64  mov     rax, [rcx]
0x18020af67  mov     rax, [rax+80h]
0x18020af6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020af73  mov     eax, [rbp+arg_0]
0x18020af76  lea     r9, [rbp+var_28]
0x18020af7a  mov     rcx, [r14+68h]
0x18020af7e  xor     r8d, r8d
0x18020af81  mov     dword ptr [rbp+var_28+0Ch], eax
0x18020af84  mov     edx, 56Eh
0x18020af89  mov     qword ptr [rbp+var_18+8], rdi
0x18020af8d  mov     [rbp+var_8], rbx
0x18020af91  mov     rax, [rcx]
0x18020af94  mov     [rsp+80h+var_60], r12
0x18020af99  mov     rax, [rax+18h]
0x18020af9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020afa2  mov     esi, eax
0x18020afa4  test    rbx, rbx
0x18020afa7  jz      short loc_18020AFB1
0x18020afa9  mov     rcx, rbx; unsigned __int16 *
0x18020afac  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x18020afb1  test    rdi, rdi
0x18020afb4  jz      short loc_18020AFBE
0x18020afb6  mov     rcx, rdi; unsigned __int16 *
0x18020afb9  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x18020afbe  mov     rcx, [rbp+arg_18]; string
0x18020afc2  call    cs:__imp_WindowsDeleteString
0x18020afc9  nop     dword ptr [rax+rax+00h]
0x18020afce  mov     rcx, [rbp+string]; string
0x18020afd2  mov     [rbp+arg_18], r12
0x18020afd6  call    cs:__imp_WindowsDeleteString
0x18020afdd  nop     dword ptr [rax+rax+00h]
0x18020afe2  lea     rcx, [rbp+var_48]; void *
0x18020afe6  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x18020afeb  mov     ebx, 3FFFFFFFh
0x18020aff0  mov     dword ptr [rbp+string], r12d
0x18020aff4  lea     rcx, [r14+98h]; this
0x18020affb  mov     dword ptr [rbp+length], ebx
0x18020affe  lea     r9, [rbp+arg_18]; int *
0x18020b002  mov     dword ptr [rbp+arg_18], r12d
0x18020b006  lea     r8, [rbp+string]; int *
0x18020b00a  lea     rdx, [rbp+length]; int *
0x18020b00e  call    ?GetChanges@CTextInputDriverNotifyChanges@@QEAA_NAEAH00@Z; CTextInputDriverNotifyChanges::GetChanges(int &,int &,int &)
0x18020b013  test    esi, esi
0x18020b015  js      short loc_18020B039
0x18020b017  mov     edx, dword ptr [rbp+length]; int
0x18020b01a  cmp     edx, ebx
0x18020b01c  jz      short loc_18020B039
0x18020b01e  mov     r9d, dword ptr [rbp+arg_18]
0x18020b022  mov     rcx, r14; this
0x18020b025  mov     r8d, dword ptr [rbp+string]
0x18020b029  sub     r9d, edx; int
0x18020b02c  sub     r8d, edx; int
0x18020b02f  mov     ebx, r12d
0x18020b032  call    ?SendTextChangedNotification@CTSF30Base@@AEAAXJJJ@Z; CTSF30Base::SendTextChangedNotification(long,long,long)
0x18020b037  jmp     short loc_18020B04F
0x18020b039  mov     rax, [r15]
0x18020b03c  mov     edx, 1
0x18020b041  mov     rcx, r15
0x18020b044  mov     rax, [rax+68h]
0x18020b048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020b04d  mov     ebx, eax
0x18020b04f  mov     rcx, [r14+68h]
0x18020b053  test    byte ptr [rcx+0B8h], 10h
0x18020b05a  jnz     short loc_18020B06F
0x18020b05c  add     rcx, 10h
0x18020b060  mov     rdx, [rcx]
0x18020b063  mov     rax, [rdx+0A8h]
0x18020b06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020b06f  mov     eax, ebx
0x18020b071  mov     [r14+70h], r12b
0x18020b075  add     rsp, 80h
0x18020b07c  pop     r15
0x18020b07e  pop     r14
0x18020b080  pop     r12
0x18020b082  pop     rdi
0x18020b083  pop     rsi
0x18020b084  pop     rbx
0x18020b085  pop     rbp
0x18020b086  retn
```
