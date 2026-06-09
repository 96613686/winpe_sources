# CImpISecurityInfo::GetCurrentTrustee(_TRUSTEE_W * *)

- ea: `0x100434f0`
- end: `0x100435b6`
- name: `?GetCurrentTrustee@CImpISecurityInfo@@UAGJPAPAU_TRUSTEE_W@@@Z`
- size: `198`
- prototype: `int(CImpISecurityInfo *__hidden this, struct _TRUSTEE_W **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x1001f2d0`
- `0x100434f0`
- `0x10043a70`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1004359b`
- `KERNEL32!LeaveCriticalSection` at `0x1004359b`
- `KERNEL32!EnterCriticalSection` at `0x10043530`
- `KERNEL32!EnterCriticalSection` at `0x10043530`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004351d`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004351d`

## pseudocode

```c
int __userpurge CImpISecurityInfo::GetCurrentTrustee@<eax>(
        const unsigned __int16 *a1@<ebx>,
        CImpISecurityInfo *this,
        struct _TRUSTEE_W **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // edi
  JoltProperties *v5; // edi
  enum _TRUSTEE_TYPE v6; // ecx
  unsigned __int16 *v7; // eax
  const struct _GUID *v9; // [esp+0h] [ebp-20h]
  int v10; // [esp+4h] [ebp-1Ch]
  unsigned int v11[4]; // [esp+10h] [ebp-10h] BYREF

  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  v11[3] = 0;
  if ( a3 )
  {
    v5 = *(JoltProperties **)(*((_DWORD *)this + 2) + 160);
    if ( JoltProperties::BinarySearch(v5, 0xCu, v11) < 0 )
    {
      v7 = 0;
    }
    else
    {
      v6 = 48 * v11[0];
      v7 = *(unsigned __int16 **)(*((_DWORD *)v5 + 4) + 48 * v11[0] + 24);
    }
    v4 = CSecuritySession::ConvertStringToTrustee(a1, v7, a3, v6);
    if ( v4 >= 0 )
      goto LABEL_8;
  }
  else
  {
    v4 = -2147024809;
  }
  CExtError::SendHRtoOLEAuto(v4, (__int128 *)&IID_ISecurityInfo, 0, v9, v10);
LABEL_8:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v4;
}

```

## disassembly

```asm
0x100434f0  mov     edi, edi
0x100434f2  push    ebp
0x100434f3  mov     ebp, esp
0x100434f5  push    0FFFFFFFFh
0x100434f7  push    offset ?GetCurrentTrustee@CImpISecurityInfo@@UAGJPAPAU_TRUSTEE_W@@@Z_SEH
0x100434fc  mov     eax, large fs:0
0x10043502  push    eax
0x10043503  sub     esp, 8
0x10043506  push    esi
0x10043507  push    edi; int
0x10043508  mov     eax, ___security_cookie
0x1004350d  xor     eax, ebp
0x1004350f  push    eax; struct _GUID *
0x10043510  lea     eax, [ebp+var_C]
0x10043513  mov     large fs:0, eax
0x10043519  push    0; perrinfo
0x1004351b  push    0; dwReserved
0x1004351d  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10043523  mov     edi, [ebp+this]
0x10043526  mov     esi, [edi+8]
0x10043529  add     esi, 64h ; 'd'
0x1004352c  push    esi; lpCriticalSection
0x1004352d  mov     [ebp+var_14], esi
0x10043530  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10043536  cmp     [ebp+arg_4], 0
0x1004353a  mov     [ebp+var_4], 0
0x10043541  jnz     short loc_1004354A
0x10043543  mov     edi, 80070057h
0x10043548  jmp     short loc_10043588
0x1004354a  mov     eax, [edi+8]
0x1004354d  mov     edi, [eax+0A0h]
0x10043553  lea     eax, [ebp+var_10]
0x10043556  push    eax; unsigned int *
0x10043557  push    0Ch; unsigned int
0x10043559  mov     ecx, edi; this
0x1004355b  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10043560  test    eax, eax
0x10043562  js      short loc_10043576
0x10043564  mov     eax, [ebp+var_10]
0x10043567  lea     ecx, [eax+eax*2]
0x1004356a  mov     eax, [edi+10h]
0x1004356d  shl     ecx, 4
0x10043570  mov     eax, [eax+ecx+18h]
0x10043574  jmp     short loc_10043578
0x10043576  xor     eax, eax
0x10043578  push    ecx; enum _TRUSTEE_TYPE
0x10043579  push    [ebp+arg_4]; struct _TRUSTEE_W **
0x1004357c  push    eax; unsigned __int16 *
0x1004357d  call    ?ConvertStringToTrustee@CSecuritySession@@QAEJPAGPAPAU_TRUSTEE_W@@W4_TRUSTEE_TYPE@@@Z; CSecuritySession::ConvertStringToTrustee(ushort *,_TRUSTEE_W * *,_TRUSTEE_TYPE)
0x10043582  mov     edi, eax
0x10043584  test    edi, edi
0x10043586  jns     short loc_10043596
0x10043588  push    0; int
0x1004358a  push    offset _IID_ISecurityInfo; int
0x1004358f  mov     edx, edi
0x10043591  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10043596  test    esi, esi
0x10043598  jz      short loc_100435A1
0x1004359a  push    esi; lpCriticalSection
0x1004359b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100435a1  mov     eax, edi
0x100435a3  mov     ecx, [ebp+var_C]
0x100435a6  mov     large fs:0, ecx
0x100435ad  pop     ecx
0x100435ae  pop     edi
0x100435af  pop     esi
0x100435b0  mov     esp, ebp
0x100435b2  pop     ebp
0x100435b3  retn    8
0x1004ead0  lea     ecx, [ebp+var_14]; this
0x1004ead3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004eadd  nop
0x1004eade  nop
0x1004eadf  mov     edx, [esp-4+arg_4]
0x1004eae3  lea     eax, [edx+0Ch]
0x1004eae6  mov     ecx, [edx-14h]
0x1004eae9  xor     ecx, eax; StackCookie
0x1004eaeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004eaf0  mov     eax, offset stru_1004FD68
0x1004eaf5  jmp     ___CxxFrameHandler3
```
