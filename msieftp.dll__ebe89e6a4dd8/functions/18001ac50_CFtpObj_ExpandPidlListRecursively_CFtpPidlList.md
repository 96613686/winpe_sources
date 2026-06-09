# CFtpObj::_ExpandPidlListRecursively(CFtpPidlList *)

- ea: `0x18001ac50`
- end: `0x18001ae36`
- name: `?_ExpandPidlListRecursively@CFtpObj@@IEAAPEAVCFtpPidlList@@PEAV2@@Z`
- size: `486`
- prototype: `struct CFtpPidlList *(CFtpObj *__hidden this, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001b048`

## callees

- `0x1800170bc`
- `0x18001ac50`
- `0x18001ddf4`
- `0x18001e1cc`
- `0x18001fa30`
- `0x18001fc24`
- `0x180024178`
- `0x180024ac8`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18001ad35`
- `SHELL32!__imp_ILClone` at `0x18001ad35`
- `SHELL32!__imp_ILGetSize` at `0x18001ad46`
- `SHELL32!__imp_ILGetSize` at `0x18001ad46`
- `SHELL32!__imp_ILFree` at `0x18001ad8b`
- `SHELL32!__imp_ILFree` at `0x18001ad8b`

## pseudocode

```c
struct CFtpPidlList *__fastcall CFtpObj::_ExpandPidlListRecursively(CFtpObj *this, struct CFtpPidlList *a2)
{
  struct CFtpDir *v2; // rax
  __int64 v4; // rcx
  __int64 v6; // rax
  struct CFtpDir *v7; // rcx
  struct CFtpDir *v8; // rdx
  __int64 v9; // r8
  CFtpSite *v10; // rcx
  int Hint; // edi
  const ITEMIDLIST *v12; // rax
  ITEMIDLIST *v13; // rsi
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  struct GLOBALTIMEOUTINFO **v17; // rcx
  int v18; // edx
  unsigned int v19; // r9d
  unsigned int v21; // [rsp+28h] [rbp-48h]
  unsigned int v22; // [rsp+30h] [rbp-40h]
  struct CFtpPidlList *v23; // [rsp+50h] [rbp-20h] BYREF
  struct CFtpDir *v24[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 WireEncoding; // [rsp+68h] [rbp-8h]
  void *v26; // [rsp+90h] [rbp+20h] BYREF

  v2 = (struct CFtpDir *)*((_QWORD *)this + 11);
  v4 = *((_QWORD *)this + 5);
  v24[1] = v2;
  v24[0] = 0;
  v23 = 0;
  WireEncoding = (unsigned int)CFtpFolder::GetWireEncoding(v4);
  if ( CFtpPidlList_Create(0, 0, &v23) >= 0 )
  {
    v6 = *((_QWORD *)this + 5);
    v7 = 0;
    v24[0] = 0;
    v8 = *(struct CFtpDir **)(v6 + 128);
    if ( v8 )
    {
      IUnknown_Set(v24, v8);
      v7 = v24[0];
    }
    v9 = *((_QWORD *)this + 6);
    if ( v9 )
    {
      if ( v7 )
      {
        v10 = *(CFtpSite **)(v9 + 16);
        v26 = 0;
        if ( !v10 )
        {
          Hint = -2147467259;
LABEL_18:
          if ( !*((_DWORD *)this + 33) )
          {
            (*(void (__fastcall **)(struct CFtpPidlList *))(*(_QWORD *)v23 + 16LL))(v23);
            v23 = 0;
            DisplayWininetErrorEx(0, v18, Hint, v19, 0x19Du, v21, v22, 0, 0);
            *((_DWORD *)this + 33) = 1;
          }
          return v23;
        }
        Hint = CFtpSite::GetHint(
                 v10,
                 0,
                 *(const struct _ITEMIDLIST **)(v9 + 40),
                 0,
                 &v26,
                 0,
                 *((struct CFtpFolder **)this + 5));
        if ( Hint < 0 )
          goto LABEL_15;
        v12 = ILClone(*(LPCITEMIDLIST *)(*((_QWORD *)this + 6) + 48LL));
        v13 = (ITEMIDLIST *)v12;
        if ( v12 )
        {
          HIDWORD(WireEncoding) = ILGetSize(v12) - 2;
          v14 = CFtpPidlList::RecursiveEnum(a2, v13, ProcessItemCB, v26, &v23);
          v15 = *((_QWORD *)this + 11);
          Hint = v14;
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
          ILFree(v13);
        }
        v16 = *((_QWORD *)this + 6);
        v17 = *(struct GLOBALTIMEOUTINFO ***)(v16 + 16);
        if ( v17 )
          CFtpSite::ReleaseHint(v17, *(const struct _ITEMIDLIST **)(v16 + 40), (struct GLOBALTIMEOUTINFO *)v26);
        (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)v24[0] + 16LL))(v24[0]);
        if ( Hint < 0 )
        {
LABEL_15:
          if ( Hint != -2147023673 )
            goto LABEL_18;
        }
      }
    }
  }
  return v23;
}

```

## disassembly

```asm
0x18001ac50  mov     [rsp-18h+arg_8], rbx
0x18001ac55  mov     [rsp-18h+arg_10], rsi
0x18001ac5a  push    rbp
0x18001ac5b  push    rdi
0x18001ac5c  push    r14
0x18001ac5e  mov     rbp, rsp
0x18001ac61  sub     rsp, 70h
0x18001ac65  mov     rax, [rcx+58h]
0x18001ac69  mov     rbx, rcx
0x18001ac6c  mov     rcx, [rcx+28h]
0x18001ac70  mov     r14, rdx
0x18001ac73  mov     [rbp+var_10], rax
0x18001ac77  mov     [rbp+var_18], 0
0x18001ac7f  mov     [rbp+var_8], 0
0x18001ac87  mov     [rbp+var_20], 0
0x18001ac8f  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x18001ac94  lea     r8, [rbp+var_20]; struct CFtpPidlList **
0x18001ac98  mov     dword ptr [rbp+var_8], eax
0x18001ac9b  xor     edx, edx; struct _ITEMIDLIST **
0x18001ac9d  xor     ecx, ecx; int
0x18001ac9f  call    ?CFtpPidlList_Create@@YAJHQEAPEFBU_ITEMIDLIST@@PEAPEAVCFtpPidlList@@@Z; CFtpPidlList_Create(int,_ITEMIDLIST const * * const,CFtpPidlList * *)
0x18001aca4  test    eax, eax
0x18001aca6  js      loc_18001AE1D
0x18001acac  mov     rax, [rbx+28h]
0x18001acb0  xor     ecx, ecx
0x18001acb2  mov     [rbp+var_18], rcx
0x18001acb6  mov     rdx, [rax+80h]; struct CFtpDir *
0x18001acbd  test    rdx, rdx
0x18001acc0  jz      short loc_18001ACCF
0x18001acc2  lea     rcx, [rbp+var_18]; struct CFtpDir **
0x18001acc6  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18001accb  mov     rcx, [rbp+var_18]
0x18001accf  mov     r8, [rbx+30h]
0x18001acd3  test    r8, r8
0x18001acd6  jz      loc_18001AE1D
0x18001acdc  test    rcx, rcx
0x18001acdf  jz      loc_18001AE1D
0x18001ace5  mov     rcx, [r8+10h]; this
0x18001ace9  mov     [rbp+arg_0], 0
0x18001acf1  test    rcx, rcx
0x18001acf4  jz      loc_18001ADC9
0x18001acfa  mov     rax, [rbx+28h]
0x18001acfe  xor     r9d, r9d; struct CStatusBar *
0x18001ad01  mov     r8, [r8+28h]; struct _ITEMIDLIST *
0x18001ad05  xor     edx, edx; HWND
0x18001ad07  mov     [rsp+70h+var_40], rax; struct CFtpFolder *
0x18001ad0c  lea     rax, [rbp+arg_0]
0x18001ad10  mov     [rsp+70h+var_48], 0; struct IUnknown *
0x18001ad19  mov     qword ptr [rsp+70h+uID], rax; void **
0x18001ad1e  call    ?GetHint@CFtpSite@@QEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEAVCStatusBar@@PEAPEAXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpSite::GetHint(HWND__ *,_ITEMIDLIST const *,CStatusBar *,void * *,IUnknown *,CFtpFolder *)
0x18001ad23  mov     edi, eax
0x18001ad25  test    eax, eax
0x18001ad27  js      loc_18001ADBF
0x18001ad2d  mov     rcx, [rbx+30h]
0x18001ad31  mov     rcx, [rcx+30h]; pidl
0x18001ad35  call    cs:__imp_ILClone
0x18001ad3b  mov     rsi, rax
0x18001ad3e  test    rax, rax
0x18001ad41  jz      short loc_18001AD91
0x18001ad43  mov     rcx, rax; pidl
0x18001ad46  call    cs:__imp_ILGetSize
0x18001ad4c  mov     r9, [rbp+arg_0]; void *
0x18001ad50  lea     r8, ?ProcessItemCB@@YAJPEAX0PEFBU_ITEMIDLIST@@PEAH0@Z; int (*)(void *, void *, const struct _ITEMIDLIST *, int *, void *)
0x18001ad57  sub     eax, 2
0x18001ad5a  mov     rdx, rsi; struct _ITEMIDLIST *
0x18001ad5d  mov     dword ptr [rbp+var_8+4], eax
0x18001ad60  mov     rcx, r14; this
0x18001ad63  lea     rax, [rbp+var_20]
0x18001ad67  mov     qword ptr [rsp+70h+uID], rax; void *
0x18001ad6c  call    ?RecursiveEnum@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@P6AJPEAX10PEAH1@Z11@Z; CFtpPidlList::RecursiveEnum(_ITEMIDLIST const *,long (*)(void *,void *,_ITEMIDLIST const *,int *,void *),void *,void *)
0x18001ad71  mov     rcx, [rbx+58h]
0x18001ad75  mov     edi, eax
0x18001ad77  test    rcx, rcx
0x18001ad7a  jz      short loc_18001AD88
0x18001ad7c  mov     rdx, [rcx]
0x18001ad7f  mov     rax, [rdx+20h]
0x18001ad83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad88  mov     rcx, rsi; pidl
0x18001ad8b  call    cs:__imp_ILFree
0x18001ad91  mov     rdx, [rbx+30h]
0x18001ad95  mov     rcx, [rdx+10h]; this
0x18001ad99  test    rcx, rcx
0x18001ad9c  jz      short loc_18001ADAB
0x18001ad9e  mov     r8, [rbp+arg_0]; void *
0x18001ada2  mov     rdx, [rdx+28h]; struct _ITEMIDLIST *
0x18001ada6  call    ?ReleaseHint@CFtpSite@@QEAAXPEFBU_ITEMIDLIST@@PEAX@Z; CFtpSite::ReleaseHint(_ITEMIDLIST const *,void *)
0x18001adab  mov     rcx, [rbp+var_18]
0x18001adaf  mov     rax, [rcx]
0x18001adb2  mov     rax, [rax+10h]
0x18001adb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adbb  test    edi, edi
0x18001adbd  jns     short loc_18001AE1D
0x18001adbf  cmp     edi, 800704C7h
0x18001adc5  jz      short loc_18001AE1D
0x18001adc7  jmp     short loc_18001ADCE
0x18001adc9  mov     edi, 80004005h
0x18001adce  cmp     dword ptr [rbx+84h], 0
0x18001add5  jnz     short loc_18001AE1D
0x18001add7  mov     rcx, [rbp+var_20]
0x18001addb  mov     rax, [rcx]
0x18001adde  mov     rax, [rax+10h]
0x18001ade2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ade7  mov     [rsp+70h+var_30], 0; unsigned __int16 *
0x18001adf0  mov     r8d, edi; int
0x18001adf3  mov     [rsp+70h+var_38], 0; struct IProgressDialog *
0x18001adfc  xor     ecx, ecx; HWND
0x18001adfe  mov     [rsp+70h+uID], 19Dh; uID
0x18001ae06  mov     [rbp+var_20], 0
0x18001ae0e  call    ?DisplayWininetErrorEx@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@PEBG@Z; DisplayWininetErrorEx(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *,ushort const *)
0x18001ae13  mov     dword ptr [rbx+84h], 1
0x18001ae1d  mov     rax, [rbp+var_20]
0x18001ae21  lea     r11, [rsp+70h+var_s0]
0x18001ae26  mov     rbx, [r11+28h]
0x18001ae2a  mov     rsi, [r11+30h]
0x18001ae2e  mov     rsp, r11
0x18001ae31  pop     r14
0x18001ae33  pop     rdi
0x18001ae34  pop     rbp
0x18001ae35  retn
```
