# Mso::Process::TryToOpen(void)

- ea: `0x1800bc1c0`
- end: `0x1800bc292`
- name: `?TryToOpen@Process@Mso@@YA_NXZ`
- size: `210`
- prototype: `bool __fastcall(Mso::Process *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800bbf60`

## callees

- `0x18003e690`
- `0x1800bbeb4`
- `0x1800bc198`
- `0x1800bc1c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800bc26f`
- `KERNEL32!CloseHandle` at `0x1800bc26f`
- `KERNEL32!OpenEventW` at `0x1800bc242`
- `KERNEL32!OpenEventW` at `0x1800bc242`
- `ole32!StringFromCLSID` at `0x1800bc202`
- `ole32!StringFromCLSID` at `0x1800bc202`
- `ole32!CoTaskMemFree` at `0x1800bc21d`
- `ole32!CoTaskMemFree` at `0x1800bc287`
- `ole32!CoTaskMemFree` at `0x1800bc21d`
- `ole32!CoTaskMemFree` at `0x1800bc287`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Mso::Process::TryToOpen(Mso::Process *this, __int64 a2, struct _GUID *a3)
{
  LPOLESTR v3; // rcx
  __int64 v5; // rcx
  LPOLESTR v6; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-28h] BYREF
  IID rclsid; // [rsp+30h] [rbp-20h] BYREF

  rclsid = 0;
  if ( !Mso::Orapi::Read((Mso::Orapi *)&vmsoridSessionId, (const struct _msoreg *)&rclsid, a3) )
    return 0;
  lpsz = 0;
  if ( StringFromCLSID(&rclsid, &lpsz) < 0 || (hObject = OpenEventW(0x100000u, 0, lpsz)) == 0 )
  {
    v3 = lpsz;
    if ( lpsz )
    {
      lpsz = 0;
      CoTaskMemFree(v3);
    }
    return 0;
  }
  xmmword_18021C380 = (__int128)rclsid;
  Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::TransferFrom<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>(
    v5,
    &hObject);
  if ( hObject )
    CloseHandle(hObject);
  v6 = lpsz;
  if ( lpsz )
  {
    lpsz = 0;
    CoTaskMemFree(v6);
  }
  return 1;
}

```

## disassembly

```asm
0x1800bc1c0  push    rbp
0x1800bc1c2  mov     rbp, rsp
0x1800bc1c5  sub     rsp, 50h
0x1800bc1c9  mov     rax, cs:__security_cookie
0x1800bc1d0  xor     rax, rsp
0x1800bc1d3  mov     [rbp+var_10], rax
0x1800bc1d7  xorps   xmm0, xmm0
0x1800bc1da  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x1800bc1de  lea     rdx, [rbp+rclsid]; struct _msoreg *
0x1800bc1e2  lea     rcx, ?vmsoridSessionId@@3U_msoreg@@B; this
0x1800bc1e9  call    ?Read@Orapi@Mso@@YA_NAEBU_msoreg@@AEAU_GUID@@@Z; Mso::Orapi::Read(_msoreg const &,_GUID &)
0x1800bc1ee  test    al, al
0x1800bc1f0  jz      short loc_1800BC223
0x1800bc1f2  mov     [rbp+lpsz], 0
0x1800bc1fa  lea     rdx, [rbp+lpsz]; lplpsz
0x1800bc1fe  lea     rcx, [rbp+rclsid]; rclsid
0x1800bc202  call    cs:__imp_StringFromCLSID
0x1800bc208  test    eax, eax
0x1800bc20a  jns     short loc_1800BC237
0x1800bc20c  mov     rcx, [rbp+lpsz]; pv
0x1800bc210  test    rcx, rcx
0x1800bc213  jz      short loc_1800BC223
0x1800bc215  mov     [rbp+lpsz], 0
0x1800bc21d  call    cs:__imp_CoTaskMemFree
0x1800bc223  xor     al, al
0x1800bc225  mov     rcx, [rbp+var_10]
0x1800bc229  xor     rcx, rsp; StackCookie
0x1800bc22c  call    __security_check_cookie
0x1800bc231  add     rsp, 50h
0x1800bc235  pop     rbp
0x1800bc236  retn
0x1800bc237  mov     r8, [rbp+lpsz]; lpName
0x1800bc23b  xor     edx, edx; bInheritHandle
0x1800bc23d  mov     ecx, 100000h; dwDesiredAccess
0x1800bc242  call    cs:__imp_OpenEventW
0x1800bc248  mov     [rbp+hObject], rax
0x1800bc24c  test    rax, rax
0x1800bc24f  jz      short loc_1800BC20C
0x1800bc251  movups  xmm0, xmmword ptr [rbp+rclsid.Data1]
0x1800bc255  movdqu  cs:xmmword_18021C380, xmm0
0x1800bc25d  lea     rdx, [rbp+hObject]
0x1800bc261  call    ??$TransferFrom@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXAEAV01@@Z; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::TransferFrom<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>(Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>> &)
0x1800bc266  mov     rcx, [rbp+hObject]; hObject
0x1800bc26a  test    rcx, rcx
0x1800bc26d  jz      short loc_1800BC276
0x1800bc26f  call    cs:__imp_CloseHandle
0x1800bc275  nop
0x1800bc276  mov     rcx, [rbp+lpsz]; pv
0x1800bc27a  test    rcx, rcx
0x1800bc27d  jz      short loc_1800BC28D
0x1800bc27f  mov     [rbp+lpsz], 0
0x1800bc287  call    cs:__imp_CoTaskMemFree
0x1800bc28d  mov     al, 1
0x1800bc28f  jmp     short loc_1800BC225
```
