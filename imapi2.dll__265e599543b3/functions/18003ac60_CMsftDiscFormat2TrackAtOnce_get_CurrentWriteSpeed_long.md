# CMsftDiscFormat2TrackAtOnce::get_CurrentWriteSpeed(long *)

- ea: `0x18003ac60`
- end: `0x18003ad1a`
- name: `?get_CurrentWriteSpeed@CMsftDiscFormat2TrackAtOnce@@UEAAJPEAJ@Z`
- size: `186`
- prototype: `__int64 __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18003a144`
- `0x18003ac60`
- `0x180043f38`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::get_CurrentWriteSpeed(
        Imapi2Utility **this,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE *a2)
{
  signed int CurrentDriveSpeedProperties; // ebx
  __int64 v5; // rcx
  const struct _GUID *v6; // r8
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v7; // eax
  _IMAPI_MEDIA_PHYSICAL_TYPE v9[10]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+10h] BYREF
  struct IDiscRecorder2 *v11; // [rsp+70h] [rbp+18h] BYREF
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v12; // [rsp+78h] [rbp+20h] BYREF

  v9[0] = IMAPI_MEDIA_TYPE_UNKNOWN;
  v12 = IMAPI_MEDIA_TYPE_UNKNOWN;
  LOWORD(v10) = 0;
  LODWORD(v11) = 0;
  if ( a2 )
  {
    CurrentDriveSpeedProperties = CMsftDiscFormat2TrackAtOnce::ValidateRecorderSet((CMsftDiscFormat2TrackAtOnce *)this);
    if ( CurrentDriveSpeedProperties >= 0 )
    {
      CurrentDriveSpeedProperties = (*(__int64 (__fastcall **)(__int64, struct IDiscRecorder2 **))(*(_QWORD *)v5 + 224LL))(
                                      v5,
                                      &v11);
      if ( CurrentDriveSpeedProperties >= 0 )
      {
        CurrentDriveSpeedProperties = Imapi2Utility::GetCurrentDriveSpeedProperties(
                                        this[23],
                                        (struct IDiscRecorder2 *)(unsigned int)v11,
                                        (unsigned int *)&v12,
                                        v9,
                                        &v10);
        if ( CurrentDriveSpeedProperties >= 0 )
        {
          v7 = v12;
          if ( (unsigned int)v12 > 0x7FFFFFFF )
            v7 = 0x7FFFFFFF;
          *a2 = v7;
        }
      }
    }
    if ( (CurrentDriveSpeedProperties & 0x80FF0000) == 0x80AA0000 )
      Imapi2Utility::SetErrorDescription(CurrentDriveSpeedProperties, (__int64)&CLSID_MsftDiscFormat2TrackAtOnce, v6);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)CurrentDriveSpeedProperties;
}

```

## disassembly

```asm
0x18003ac60  push    rbx
0x18003ac62  push    rsi
0x18003ac63  push    rdi
0x18003ac64  sub     rsp, 40h
0x18003ac68  xor     eax, eax
0x18003ac6a  mov     [rsp+58h+var_28], 0
0x18003ac72  mov     [rsp+58h+arg_18], 0
0x18003ac7a  mov     rsi, rdx
0x18003ac7d  mov     word ptr [rsp+58h+arg_8], ax
0x18003ac82  mov     rdi, rcx
0x18003ac85  mov     dword ptr [rsp+58h+arg_10], eax
0x18003ac89  test    rdx, rdx
0x18003ac8c  jnz     short loc_18003AC95
0x18003ac8e  mov     ebx, 80004003h
0x18003ac93  jmp     short loc_18003AD10
0x18003ac95  call    ?ValidateRecorderSet@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ; CMsftDiscFormat2TrackAtOnce::ValidateRecorderSet(void)
0x18003ac9a  mov     ebx, eax
0x18003ac9c  test    eax, eax
0x18003ac9e  js      short loc_18003ACF4
0x18003aca0  mov     rax, [rcx]
0x18003aca3  lea     rdx, [rsp+58h+arg_10]
0x18003aca8  mov     rax, [rax+0E0h]
0x18003acaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acb4  mov     ebx, eax
0x18003acb6  test    eax, eax
0x18003acb8  js      short loc_18003ACF4
0x18003acba  mov     edx, dword ptr [rsp+58h+arg_10]; struct IDiscRecorder2 *
0x18003acbe  lea     rax, [rsp+58h+arg_8]
0x18003acc3  mov     rcx, [rdi+0B8h]; this
0x18003acca  lea     r9, [rsp+58h+var_28]; unsigned int *
0x18003accf  lea     r8, [rsp+58h+arg_18]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x18003acd4  mov     [rsp+58h+var_38], rax; unsigned int *
0x18003acd9  call    ?GetCurrentDriveSpeedProperties@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK2PEAF@Z; Imapi2Utility::GetCurrentDriveSpeedProperties(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,short *)
0x18003acde  mov     ebx, eax
0x18003ace0  test    eax, eax
0x18003ace2  js      short loc_18003ACF4
0x18003ace4  mov     eax, [rsp+58h+arg_18]
0x18003ace8  mov     ecx, 7FFFFFFFh
0x18003aced  cmp     eax, ecx
0x18003acef  cmova   eax, ecx
0x18003acf2  mov     [rsi], eax
0x18003acf4  mov     eax, ebx
0x18003acf6  and     eax, 80FF0000h
0x18003acfb  cmp     eax, 80AA0000h
0x18003ad00  jnz     short loc_18003AD10
0x18003ad02  lea     rdx, CLSID_MsftDiscFormat2TrackAtOnce; int
0x18003ad09  mov     ecx, ebx; dwMessageId
0x18003ad0b  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18003ad10  mov     eax, ebx
0x18003ad12  add     rsp, 40h
0x18003ad16  pop     rdi
0x18003ad17  pop     rsi
0x18003ad18  pop     rbx
0x18003ad19  retn
```
