# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(ushort const *,ushort const *)

- ea: `0x18000354c`
- end: `0x18000376a`
- name: `?DownloadSettingsFromCommonClient@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `542`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800055f4`

## callees

- `0x180002cc4`
- `0x18000312c`
- `0x18000354c`
- `0x180003770`
- `0x180003894`
- `0x1800051b4`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180003691`
- `msvcrt!wcsrchr` at `0x180003691`
- `msvcrt!_wcsicmp` at `0x1800035be`
- `msvcrt!_wcsicmp` at `0x1800035be`
- `KERNEL32!GetProcessHeap` at `0x18000370d`
- `KERNEL32!GetProcessHeap` at `0x180003728`
- `KERNEL32!GetProcessHeap` at `0x18000370d`
- `KERNEL32!GetProcessHeap` at `0x180003728`
- `KERNEL32!HeapFree` at `0x18000371d`
- `KERNEL32!HeapFree` at `0x180003736`
- `KERNEL32!HeapFree` at `0x18000371d`
- `KERNEL32!HeapFree` at `0x180003736`

## string_xrefs

- `0x1800035ab`: `settings-win-ppe.data.microsoft.com`
- `0x1800035b7`: `settings-win.data.microsoft.com`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsFromCommonClient(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  wchar_t *v4; // rbx
  BOOL v5; // r12d
  OneCore::Base::Telemetry::OneSettingsQuery *v6; // rcx
  const unsigned __int16 *v7; // rdx
  int Headers; // edi
  unsigned int v9; // r8d
  int v10; // r15d
  int v11; // eax
  wchar_t *v12; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v13; // rcx
  __int64 v14; // r9
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h] BYREF
  void *v20; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v22[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23[264]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int16 v24[512]; // [rsp+480h] [rbp+380h] BYREF

  v20 = 0;
  v18 = 0;
  memset_0(v24, 0, sizeof(v24));
  v4 = 0;
  lpMem = 0;
  Str = 0;
  v23[0] = 0;
  v22[0] = 0;
  v5 = _wcsicmp(L"settings-win.data.microsoft.com", L"settings-win-ppe.data.microsoft.com") == 0;
  OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(v6, &v20, &v18);
  Headers = OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(this, v7, (unsigned __int16 **)&lpMem);
  if ( Headers >= 0 )
  {
    Headers = OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(this, v24, v9);
    if ( Headers >= 0 )
    {
      v10 = v18;
      v11 = OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(
              this,
              (void *)((unsigned __int64)v20 & -(__int64)(v18 != 0)),
              (const unsigned __int16 *)lpMem,
              v24,
              v5,
              0,
              0,
              &Str);
      v4 = Str;
      Headers = v11;
      if ( v11 == -2147024891 && Str && *Str && (*Str != 58 || Str[1]) )
      {
        v12 = wcsrchr(Str, 0x3Au);
        if ( v12 )
          *v12 = 0;
        if ( !(unsigned int)OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(
                              v13,
                              v4,
                              v22,
                              v14,
                              v23)
          && v22[0] )
        {
          Headers = OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(
                      this,
                      (void *)((unsigned __int64)v20 & -(__int64)(v10 != 0)),
                      (const unsigned __int16 *)lpMem,
                      v24,
                      v5,
                      v22,
                      v23,
                      0);
        }
      }
    }
  }
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v4 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v4);
  }
  return (unsigned int)Headers;
}

```

## disassembly

```asm
0x18000354c  mov     [rsp-8+arg_8], rbx
0x180003551  mov     [rsp-8+arg_10], rdi
0x180003556  push    rbp
0x180003557  push    r12
0x180003559  push    r13
0x18000355b  push    r14
0x18000355d  push    r15
0x18000355f  lea     rbp, [rsp-790h]
0x180003567  sub     rsp, 890h
0x18000356e  mov     rax, cs:__security_cookie
0x180003575  xor     rax, rsp
0x180003578  mov     [rbp+7B0h+var_30], rax
0x18000357f  mov     r14, rcx
0x180003582  xor     r13d, r13d
0x180003585  lea     rcx, [rbp+7B0h+var_430]; void *
0x18000358c  mov     [rsp+8B0h+var_860], r13
0x180003591  xor     edx, edx; Val
0x180003593  mov     [rsp+8B0h+var_870], r13d
0x180003598  mov     r8d, 400h; Size
0x18000359e  call    memset_0
0x1800035a3  mov     ebx, r13d
0x1800035a6  mov     [rsp+8B0h+lpMem], r13
0x1800035ab  lea     rdx, aSettingsWinPpe; "settings-win-ppe.data.microsoft.com"
0x1800035b2  mov     [rsp+8B0h+Str], rbx
0x1800035b7  lea     rcx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x1800035be  call    cs:__imp__wcsicmp
0x1800035c4  mov     r12d, r13d
0x1800035c7  mov     [rbp+7B0h+var_640], r13w
0x1800035cf  test    eax, eax
0x1800035d1  mov     [rsp+8B0h+var_850], r13w
0x1800035d7  lea     r8, [rsp+8B0h+var_870]; int *
0x1800035dc  lea     rdx, [rsp+8B0h+var_860]; void **
0x1800035e1  setz    r12b
0x1800035e5  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x1800035ea  lea     r8, [rsp+8B0h+lpMem]; unsigned __int16 **
0x1800035ef  mov     rcx, r14; this
0x1800035f2  call    ?CreateHeaders@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::CreateHeaders(ushort const *,ushort * *)
0x1800035f7  mov     edi, eax
0x1800035f9  test    eax, eax
0x1800035fb  js      loc_180003706
0x180003601  lea     rdx, [rbp+7B0h+var_430]; unsigned __int16 *
0x180003608  mov     rcx, r14; this
0x18000360b  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x180003610  mov     edi, eax
0x180003612  test    eax, eax
0x180003614  js      loc_180003706
0x18000361a  mov     r15d, [rsp+8B0h+var_870]
0x18000361f  lea     r9, [rbp+7B0h+var_430]; unsigned __int16 *
0x180003626  mov     r8, [rsp+8B0h+lpMem]; unsigned __int16 *
0x18000362b  mov     eax, r15d
0x18000362e  neg     eax
0x180003630  mov     rcx, r14; this
0x180003633  lea     rax, [rsp+8B0h+Str]
0x180003638  mov     [rsp+8B0h+var_878], rax; unsigned __int16 **
0x18000363d  sbb     rdx, rdx
0x180003640  and     rdx, [rsp+8B0h+var_860]; void *
0x180003645  mov     [rsp+8B0h+var_880], r13; unsigned __int16 *
0x18000364a  mov     [rsp+8B0h+var_888], r13; unsigned __int64
0x18000364f  mov     dword ptr [rsp+8B0h+var_890], r12d; int
0x180003654  call    ?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)
0x180003659  mov     rbx, [rsp+8B0h+Str]
0x18000365e  mov     edi, eax
0x180003660  cmp     eax, 80070005h
0x180003665  jnz     loc_180003706
0x18000366b  test    rbx, rbx
0x18000366e  jz      loc_180003706
0x180003674  cmp     [rbx], r13w
0x180003678  jz      loc_180003706
0x18000367e  lea     edx, [r13+3Ah]; Ch
0x180003682  cmp     [rbx], dx
0x180003685  jnz     short loc_18000368E
0x180003687  cmp     [rbx+2], r13w
0x18000368c  jz      short loc_180003706
0x18000368e  mov     rcx, rbx; Str
0x180003691  call    cs:__imp_wcsrchr
0x180003697  test    rax, rax
0x18000369a  jz      short loc_1800036A0
0x18000369c  mov     [rax], r13w
0x1800036a0  lea     rax, [rbp+7B0h+var_640]
0x1800036a7  mov     rdx, rbx; unsigned __int16 *
0x1800036aa  lea     r8, [rsp+8B0h+var_850]; unsigned __int16 *
0x1800036af  mov     [rsp+8B0h+var_890], rax; unsigned __int16 *
0x1800036b4  call    ?GetCredentialsForBasicProxyIfPresent@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBGPEAG_K12@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetCredentialsForBasicProxyIfPresent(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x1800036b9  test    eax, eax
0x1800036bb  jnz     short loc_180003706
0x1800036bd  cmp     r13w, [rsp+8B0h+var_850]
0x1800036c3  jz      short loc_180003706
0x1800036c5  mov     r8, [rsp+8B0h+lpMem]; unsigned __int16 *
0x1800036ca  lea     rax, [rbp+7B0h+var_640]
0x1800036d1  mov     [rsp+8B0h+var_878], r13; unsigned __int16 **
0x1800036d6  lea     r9, [rbp+7B0h+var_430]; unsigned __int16 *
0x1800036dd  mov     [rsp+8B0h+var_880], rax; unsigned __int16 *
0x1800036e2  neg     r15d
0x1800036e5  lea     rax, [rsp+8B0h+var_850]
0x1800036ea  mov     rcx, r14; this
0x1800036ed  sbb     rdx, rdx
0x1800036f0  mov     [rsp+8B0h+var_888], rax; unsigned __int16 *
0x1800036f5  and     rdx, [rsp+8B0h+var_860]; void *
0x1800036fa  mov     dword ptr [rsp+8B0h+var_890], r12d; int
0x1800036ff  call    ?PerformCommonClientDownload@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAXPEBG1H11PEAPEAG@Z; OneCore::Base::Telemetry::OneSettingsQuery::PerformCommonClientDownload(void *,ushort const *,ushort const *,int,ushort const *,ushort const *,ushort * *)
0x180003704  mov     edi, eax
0x180003706  cmp     [rsp+8B0h+lpMem], r13
0x18000370b  jz      short loc_180003723
0x18000370d  call    cs:__imp_GetProcessHeap
0x180003713  mov     r8, [rsp+8B0h+lpMem]; lpMem
0x180003718  xor     edx, edx; dwFlags
0x18000371a  mov     rcx, rax; hHeap
0x18000371d  call    cs:__imp_HeapFree
0x180003723  test    rbx, rbx
0x180003726  jz      short loc_18000373C
0x180003728  call    cs:__imp_GetProcessHeap
0x18000372e  mov     r8, rbx; lpMem
0x180003731  xor     edx, edx; dwFlags
0x180003733  mov     rcx, rax; hHeap
0x180003736  call    cs:__imp_HeapFree
0x18000373c  mov     eax, edi
0x18000373e  mov     rcx, [rbp+7B0h+var_30]
0x180003745  xor     rcx, rsp; StackCookie
0x180003748  call    __security_check_cookie
0x18000374d  lea     r11, [rsp+8B0h+var_20]
0x180003755  mov     rbx, [r11+38h]
0x180003759  mov     rdi, [r11+40h]
0x18000375d  mov     rsp, r11
0x180003760  pop     r15
0x180003762  pop     r14
0x180003764  pop     r13
0x180003766  pop     r12
0x180003768  pop     rbp
0x180003769  retn
```
