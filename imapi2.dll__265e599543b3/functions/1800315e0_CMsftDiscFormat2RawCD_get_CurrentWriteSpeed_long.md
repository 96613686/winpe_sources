# CMsftDiscFormat2RawCD::get_CurrentWriteSpeed(long *)

- ea: `0x1800315e0`
- end: `0x18003169a`
- name: `?get_CurrentWriteSpeed@CMsftDiscFormat2RawCD@@UEAAJPEAJ@Z`
- size: `186`
- prototype: `__int64 __fastcall(CMsftDiscFormat2RawCD *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x180030500`
- `0x1800315e0`
- `0x180043f38`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2RawCD::get_CurrentWriteSpeed(
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
    CurrentDriveSpeedProperties = CMsftDiscFormat2RawCD::ValidateRecorderSet((CMsftDiscFormat2RawCD *)this);
    if ( CurrentDriveSpeedProperties >= 0 )
    {
      CurrentDriveSpeedProperties = (*(__int64 (__fastcall **)(__int64, struct IDiscRecorder2 **))(*(_QWORD *)v5 + 192LL))(
                                      v5,
                                      &v11);
      if ( CurrentDriveSpeedProperties >= 0 )
      {
        CurrentDriveSpeedProperties = Imapi2Utility::GetCurrentDriveSpeedProperties(
                                        this[22],
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
      Imapi2Utility::SetErrorDescription(CurrentDriveSpeedProperties, (__int64)&CLSID_MsftDiscFormat2RawCD, v6);
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
0x1800315e0  push    rbx
0x1800315e2  push    rsi
0x1800315e3  push    rdi
0x1800315e4  sub     rsp, 40h
0x1800315e8  xor     eax, eax
0x1800315ea  mov     [rsp+58h+var_28], 0
0x1800315f2  mov     [rsp+58h+arg_18], 0
0x1800315fa  mov     rsi, rdx
0x1800315fd  mov     word ptr [rsp+58h+arg_8], ax
0x180031602  mov     rdi, rcx
0x180031605  mov     dword ptr [rsp+58h+arg_10], eax
0x180031609  test    rdx, rdx
0x18003160c  jnz     short loc_180031615
0x18003160e  mov     ebx, 80004003h
0x180031613  jmp     short loc_180031690
0x180031615  call    ?ValidateRecorderSet@CMsftDiscFormat2RawCD@@AEAAJXZ; CMsftDiscFormat2RawCD::ValidateRecorderSet(void)
0x18003161a  mov     ebx, eax
0x18003161c  test    eax, eax
0x18003161e  js      short loc_180031674
0x180031620  mov     rax, [rcx]
0x180031623  lea     rdx, [rsp+58h+arg_10]
0x180031628  mov     rax, [rax+0C0h]
0x18003162f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031634  mov     ebx, eax
0x180031636  test    eax, eax
0x180031638  js      short loc_180031674
0x18003163a  mov     edx, dword ptr [rsp+58h+arg_10]; struct IDiscRecorder2 *
0x18003163e  lea     rax, [rsp+58h+arg_8]
0x180031643  mov     rcx, [rdi+0B0h]; this
0x18003164a  lea     r9, [rsp+58h+var_28]; unsigned int *
0x18003164f  lea     r8, [rsp+58h+arg_18]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180031654  mov     [rsp+58h+var_38], rax; unsigned int *
0x180031659  call    ?GetCurrentDriveSpeedProperties@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK2PEAF@Z; Imapi2Utility::GetCurrentDriveSpeedProperties(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,short *)
0x18003165e  mov     ebx, eax
0x180031660  test    eax, eax
0x180031662  js      short loc_180031674
0x180031664  mov     eax, [rsp+58h+arg_18]
0x180031668  mov     ecx, 7FFFFFFFh
0x18003166d  cmp     eax, ecx
0x18003166f  cmova   eax, ecx
0x180031672  mov     [rsi], eax
0x180031674  mov     eax, ebx
0x180031676  and     eax, 80FF0000h
0x18003167b  cmp     eax, 80AA0000h
0x180031680  jnz     short loc_180031690
0x180031682  lea     rdx, CLSID_MsftDiscFormat2RawCD; int
0x180031689  mov     ecx, ebx; dwMessageId
0x18003168b  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180031690  mov     eax, ebx
0x180031692  add     rsp, 40h
0x180031696  pop     rdi
0x180031697  pop     rsi
0x180031698  pop     rbx
0x180031699  retn
```
