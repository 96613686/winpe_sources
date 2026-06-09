# CFtpMenu::_InvokeDownloadVerb(_CMINVOKECOMMANDINFO *)

- ea: `0x18000f9f4`
- end: `0x18000fae4`
- name: `?_InvokeDownloadVerb@CFtpMenu@@IEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CFtpMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e4c0`

## callees

- `0x180002240`
- `0x180002610`
- `0x18000d3f0`
- `0x18000eb7c`
- `0x18000f9f4`
- `0x180022fb0`
- `0x180023adc`
- `0x180024ac8`
- `0x180026f48`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18000fa9e`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000fa9e`

## pseudocode

```c
__int64 __fastcall CFtpMenu::_InvokeDownloadVerb(
        CFtpMenu *this,
        struct _CMINVOKECOMMANDINFO *a2,
        __int64 a3,
        unsigned int a4)
{
  struct CFtpDir **v6; // rax
  struct CFtpDir **v7; // rdi
  struct CFtpDir *v8; // rbx
  WCHAR psz[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( (unsigned int)ZoneCheckPidlAction(
                       *((struct IUnknown **)this + 2),
                       (unsigned int)a2,
                       (const struct _ITEMIDLIST *)(*(_QWORD *)(*((_QWORD *)this + 5) + 48LL)
                                                  + *(int *)(*((_QWORD *)this + 5) + 64LL)),
                       a4) )
  {
    if ( !(unsigned int)ShowDownloadDialog(a2->hwnd, psz) )
    {
      v6 = (struct CFtpDir **)operator new(0x20u);
      v7 = v6;
      if ( v6 )
      {
        v8 = (struct CFtpDir *)*((_QWORD *)this + 4);
        IUnknown_Set(v6, this);
        IUnknown_Set(v7 + 1, v8);
        Str_SetPtrW((LPWSTR *)v7 + 2, psz);
        if ( !v7[2] || !SHCreateThread(CFtpMenu::DownloadThreadProc, v7, 0xCu, 0) )
        {
          CFtpMenu::DOWNLOADTHREADINFO::~DOWNLOADTHREADINFO((CFtpMenu::DOWNLOADTHREADINFO *)v7);
          operator delete(v7, 0x20u);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f9f4  mov     [rsp+arg_10], rbx
0x18000f9f9  mov     [rsp+arg_18], rsi
0x18000f9fe  push    rdi
0x18000f9ff  sub     rsp, 240h
0x18000fa06  mov     rax, cs:__security_cookie
0x18000fa0d  xor     rax, rsp
0x18000fa10  mov     [rsp+248h+var_18], rax
0x18000fa18  mov     rax, [rcx+28h]
0x18000fa1c  mov     rsi, rcx
0x18000fa1f  mov     rcx, [rcx+10h]; struct IUnknown *
0x18000fa23  mov     rbx, rdx
0x18000fa26  movsxd  r8, dword ptr [rax+40h]
0x18000fa2a  add     r8, [rax+30h]; struct _ITEMIDLIST *
0x18000fa2e  call    ?ZoneCheckPidlAction@@YAHPEAUIUnknown@@KPEFBU_ITEMIDLIST@@K@Z; ZoneCheckPidlAction(IUnknown *,ulong,_ITEMIDLIST const *,ulong)
0x18000fa33  test    eax, eax
0x18000fa35  jz      loc_18000FABD
0x18000fa3b  mov     rcx, [rbx+8]; HWND
0x18000fa3f  lea     rdx, [rsp+248h+psz]; unsigned __int16 *
0x18000fa44  call    ?ShowDownloadDialog@@YAJPEAUHWND__@@PEAGK@Z; ShowDownloadDialog(HWND__ *,ushort *,ulong)
0x18000fa49  test    eax, eax
0x18000fa4b  jnz     short loc_18000FABD
0x18000fa4d  lea     ecx, [rax+20h]; unsigned __int64
0x18000fa50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fa55  mov     rdi, rax
0x18000fa58  test    rax, rax
0x18000fa5b  jz      short loc_18000FABD
0x18000fa5d  mov     rbx, [rsi+20h]
0x18000fa61  mov     rdx, rsi; struct CFtpDir *
0x18000fa64  mov     rcx, rax; struct CFtpDir **
0x18000fa67  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18000fa6c  lea     rcx, [rdi+8]; struct CFtpDir **
0x18000fa70  mov     rdx, rbx; struct CFtpDir *
0x18000fa73  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18000fa78  lea     rcx, [rdi+10h]; ppsz
0x18000fa7c  lea     rdx, [rsp+248h+psz]; psz
0x18000fa81  call    Str_SetPtrW
0x18000fa86  cmp     qword ptr [rdi+10h], 0
0x18000fa8b  jz      short loc_18000FAA8
0x18000fa8d  xor     r9d, r9d; pfnCallback
0x18000fa90  lea     rcx, ?DownloadThreadProc@CFtpMenu@@KAKPEAX@Z; pfnThreadProc
0x18000fa97  mov     rdx, rdi; pData
0x18000fa9a  lea     r8d, [r9+0Ch]; flags
0x18000fa9e  call    cs:__imp_SHCreateThread
0x18000faa4  test    eax, eax
0x18000faa6  jnz     short loc_18000FABD
0x18000faa8  mov     rcx, rdi; this
0x18000faab  call    ??1DOWNLOADTHREADINFO@CFtpMenu@@QEAA@XZ; CFtpMenu::DOWNLOADTHREADINFO::~DOWNLOADTHREADINFO(void)
0x18000fab0  mov     edx, 20h ; ' '; unsigned __int64
0x18000fab5  mov     rcx, rdi; void *
0x18000fab8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fabd  xor     eax, eax
0x18000fabf  mov     rcx, [rsp+248h+var_18]
0x18000fac7  xor     rcx, rsp; StackCookie
0x18000faca  call    __security_check_cookie
0x18000facf  lea     r11, [rsp+248h+var_8]
0x18000fad7  mov     rbx, [r11+20h]
0x18000fadb  mov     rsi, [r11+28h]
0x18000fadf  mov     rsp, r11
0x18000fae2  pop     rdi
0x18000fae3  retn
```
