# CMsftDiscFormat2Data::get_CurrentWriteSpeed(long *)

- ea: `0x1800216c0`
- end: `0x18002177d`
- name: `?get_CurrentWriteSpeed@CMsftDiscFormat2Data@@UEAAJPEAJ@Z`
- size: `189`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Data *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000a804`
- `0x1800216c0`
- `0x180043f38`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::get_CurrentWriteSpeed(
        Imapi2Utility **this,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE *a2)
{
  signed int CurrentDriveSpeedProperties; // ebx
  const struct _GUID *v5; // r8
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v6; // eax
  _IMAPI_MEDIA_PHYSICAL_TYPE v8[10]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v9; // [rsp+68h] [rbp+10h] BYREF
  struct IDiscRecorder2 *v10; // [rsp+70h] [rbp+18h] BYREF
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v11; // [rsp+78h] [rbp+20h] BYREF

  v8[0] = IMAPI_MEDIA_TYPE_UNKNOWN;
  v11 = IMAPI_MEDIA_TYPE_UNKNOWN;
  LOWORD(v9) = 0;
  LODWORD(v10) = 0;
  if ( a2 )
  {
    CurrentDriveSpeedProperties = CMsftDiscFormat2Data::ValidateRecorderSet((CMsftDiscFormat2Data *)this);
    if ( CurrentDriveSpeedProperties >= 0 )
    {
      CurrentDriveSpeedProperties = (*((__int64 (__fastcall **)(Imapi2Utility **, struct IDiscRecorder2 **))*this + 29))(
                                      this,
                                      &v10);
      if ( CurrentDriveSpeedProperties >= 0 )
      {
        CurrentDriveSpeedProperties = Imapi2Utility::GetCurrentDriveSpeedProperties(
                                        this[26],
                                        (struct IDiscRecorder2 *)(unsigned int)v10,
                                        (unsigned int *)&v11,
                                        v8,
                                        &v9);
        if ( CurrentDriveSpeedProperties >= 0 )
        {
          v6 = v11;
          if ( (unsigned int)v11 > 0x7FFFFFFF )
            v6 = 0x7FFFFFFF;
          *a2 = v6;
        }
      }
    }
    if ( (CurrentDriveSpeedProperties & 0x80FF0000) == 0x80AA0000 )
      Imapi2Utility::SetErrorDescription(CurrentDriveSpeedProperties, (__int64)&CLSID_MsftDiscFormat2Data, v5);
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
0x1800216c0  push    rbx
0x1800216c2  push    rsi
0x1800216c3  push    rdi
0x1800216c4  sub     rsp, 40h
0x1800216c8  xor     eax, eax
0x1800216ca  mov     [rsp+58h+var_28], 0
0x1800216d2  mov     [rsp+58h+arg_18], 0
0x1800216da  mov     rsi, rdx
0x1800216dd  mov     word ptr [rsp+58h+arg_8], ax
0x1800216e2  mov     rdi, rcx
0x1800216e5  mov     dword ptr [rsp+58h+arg_10], eax
0x1800216e9  test    rdx, rdx
0x1800216ec  jnz     short loc_1800216F5
0x1800216ee  mov     ebx, 80004003h
0x1800216f3  jmp     short loc_180021773
0x1800216f5  call    ?ValidateRecorderSet@CMsftDiscFormat2Data@@AEAAJXZ; CMsftDiscFormat2Data::ValidateRecorderSet(void)
0x1800216fa  mov     ebx, eax
0x1800216fc  test    eax, eax
0x1800216fe  js      short loc_180021757
0x180021700  mov     rax, [rdi]
0x180021703  lea     rdx, [rsp+58h+arg_10]
0x180021708  mov     rcx, rdi
0x18002170b  mov     rax, [rax+0E8h]
0x180021712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021717  mov     ebx, eax
0x180021719  test    eax, eax
0x18002171b  js      short loc_180021757
0x18002171d  mov     edx, dword ptr [rsp+58h+arg_10]; struct IDiscRecorder2 *
0x180021721  lea     rax, [rsp+58h+arg_8]
0x180021726  mov     rcx, [rdi+0D0h]; this
0x18002172d  lea     r9, [rsp+58h+var_28]; unsigned int *
0x180021732  lea     r8, [rsp+58h+arg_18]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180021737  mov     [rsp+58h+var_38], rax; unsigned int *
0x18002173c  call    ?GetCurrentDriveSpeedProperties@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK2PEAF@Z; Imapi2Utility::GetCurrentDriveSpeedProperties(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,short *)
0x180021741  mov     ebx, eax
0x180021743  test    eax, eax
0x180021745  js      short loc_180021757
0x180021747  mov     eax, [rsp+58h+arg_18]
0x18002174b  mov     ecx, 7FFFFFFFh
0x180021750  cmp     eax, ecx
0x180021752  cmova   eax, ecx
0x180021755  mov     [rsi], eax
0x180021757  mov     eax, ebx
0x180021759  and     eax, 80FF0000h
0x18002175e  cmp     eax, 80AA0000h
0x180021763  jnz     short loc_180021773
0x180021765  lea     rdx, CLSID_MsftDiscFormat2Data; int
0x18002176c  mov     ecx, ebx; dwMessageId
0x18002176e  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180021773  mov     eax, ebx
0x180021775  add     rsp, 40h
0x180021779  pop     rdi
0x18002177a  pop     rsi
0x18002177b  pop     rbx
0x18002177c  retn
```
