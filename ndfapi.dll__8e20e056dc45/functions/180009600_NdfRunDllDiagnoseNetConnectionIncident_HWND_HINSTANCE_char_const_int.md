# NdfRunDllDiagnoseNetConnectionIncident(HWND__ *,HINSTANCE__ *,char const *,int)

- ea: `0x180009600`
- end: `0x180009703`
- name: `?NdfRunDllDiagnoseNetConnectionIncident@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@Z`
- size: `259`
- prototype: `void __fastcall(HWND, HINSTANCE, const char *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009600`
- `0x18000a160`
- `0x18000acf0`
- `0x18000b810`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180009645`
- `KERNEL32!MultiByteToWideChar` at `0x18000968c`
- `KERNEL32!MultiByteToWideChar` at `0x180009645`
- `KERNEL32!MultiByteToWideChar` at `0x18000968c`
- `ole32!CoTaskMemAlloc` at `0x180009659`
- `ole32!CoTaskMemAlloc` at `0x180009659`
- `ole32!CLSIDFromString` at `0x1800096a6`
- `ole32!CLSIDFromString` at `0x1800096a6`
- `ole32!CoTaskMemFree` at `0x1800096e7`
- `ole32!CoTaskMemFree` at `0x1800096e7`

## pseudocode

```c
void __fastcall NdfRunDllDiagnoseNetConnectionIncident(HWND a1, HINSTANCE a2, const char *a3)
{
  int cchWideChar; // ebp
  OLECHAR *v5; // rax
  OLECHAR *lpWideCharStr; // rbx
  NDFHANDLE handle; // [rsp+30h] [rbp-68h] BYREF
  GUID id; // [rsp+40h] [rbp-58h] BYREF
  CLSID pclsid; // [rsp+50h] [rbp-48h] BYREF

  if ( a3 )
  {
    handle = 0;
    cchWideChar = MultiByteToWideChar(0, 0, a3, -1, 0, 0);
    v5 = (OLECHAR *)CoTaskMemAlloc(2LL * (cchWideChar + 1));
    lpWideCharStr = v5;
    if ( v5 )
    {
      memset_0(v5, 0, 2LL * (cchWideChar + 1));
      if ( MultiByteToWideChar(0, 0, a3, -1, lpWideCharStr, cchWideChar) )
      {
        pclsid = 0;
        if ( CLSIDFromString(lpWideCharStr, &pclsid) >= 0 )
        {
          id = pclsid;
          if ( NdfCreateNetConnectionIncident(&handle, &id) >= 0 )
          {
            NdfExecuteDiagnosis(handle, 0);
            NdfCloseIncident(handle);
          }
        }
      }
      CoTaskMemFree(lpWideCharStr);
    }
  }
}

```

## disassembly

```asm
0x180009600  test    r8, r8
0x180009603  jz      locret_180009702
0x180009609  push    rbx
0x18000960a  push    rbp
0x18000960b  push    rsi
0x18000960c  push    rdi
0x18000960d  sub     rsp, 78h
0x180009611  mov     rax, cs:__security_cookie
0x180009618  xor     rax, rsp
0x18000961b  mov     [rsp+98h+var_38], rax
0x180009620  mov     [rsp+98h+cchWideChar], 0; cchWideChar
0x180009628  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000962c  xor     edx, edx; dwFlags
0x18000962e  mov     [rsp+98h+lpWideCharStr], 0; lpWideCharStr
0x180009637  xor     ecx, ecx; CodePage
0x180009639  mov     [rsp+98h+handle], 0
0x180009642  mov     rdi, r8
0x180009645  call    cs:__imp_MultiByteToWideChar
0x18000964b  mov     ebp, eax
0x18000964d  lea     ecx, [rax+1]
0x180009650  movsxd  rsi, ecx
0x180009653  add     rsi, rsi
0x180009656  mov     rcx, rsi; cb
0x180009659  call    cs:__imp_CoTaskMemAlloc
0x18000965f  mov     rbx, rax
0x180009662  test    rax, rax
0x180009665  jz      loc_1800096ED
0x18000966b  mov     r8, rsi; Size
0x18000966e  xor     edx, edx; Val
0x180009670  mov     rcx, rax; void *
0x180009673  call    memset_0
0x180009678  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000967c  mov     [rsp+98h+cchWideChar], ebp; cchWideChar
0x180009680  mov     r8, rdi; lpMultiByteStr
0x180009683  mov     [rsp+98h+lpWideCharStr], rbx; lpWideCharStr
0x180009688  xor     edx, edx; dwFlags
0x18000968a  xor     ecx, ecx; CodePage
0x18000968c  call    cs:__imp_MultiByteToWideChar
0x180009692  test    eax, eax
0x180009694  jz      short loc_1800096E4
0x180009696  xorps   xmm0, xmm0
0x180009699  lea     rdx, [rsp+98h+pclsid]; pclsid
0x18000969e  mov     rcx, rbx; lpsz
0x1800096a1  movups  xmmword ptr [rsp+98h+pclsid.Data1], xmm0
0x1800096a6  call    cs:__imp_CLSIDFromString
0x1800096ac  test    eax, eax
0x1800096ae  js      short loc_1800096E4
0x1800096b0  movaps  xmm0, xmmword ptr [rsp+98h+pclsid.Data1]
0x1800096b5  lea     rdx, [rsp+98h+id]; id
0x1800096ba  lea     rcx, [rsp+98h+handle]; handle
0x1800096bf  movdqa  xmmword ptr [rsp+98h+id.Data1], xmm0
0x1800096c5  call    NdfCreateNetConnectionIncident
0x1800096ca  test    eax, eax
0x1800096cc  js      short loc_1800096E4
0x1800096ce  mov     rcx, [rsp+98h+handle]; handle
0x1800096d3  xor     edx, edx; hwnd
0x1800096d5  call    NdfExecuteDiagnosis
0x1800096da  mov     rcx, [rsp+98h+handle]; handle
0x1800096df  call    NdfCloseIncident
0x1800096e4  mov     rcx, rbx; pv
0x1800096e7  call    cs:__imp_CoTaskMemFree
0x1800096ed  mov     rcx, [rsp+98h+var_38]
0x1800096f2  xor     rcx, rsp; StackCookie
0x1800096f5  call    __security_check_cookie
0x1800096fa  add     rsp, 78h
0x1800096fe  pop     rdi
0x1800096ff  pop     rsi
0x180009700  pop     rbp
0x180009701  pop     rbx
0x180009702  retn
```
