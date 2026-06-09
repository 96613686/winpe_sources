# CProfileTask::CreateCacheObject(void)

- ea: `0x180014a60`
- end: `0x180014b87`
- name: `?CreateCacheObject@CProfileTask@@QEAAJXZ`
- size: `295`
- prototype: `__int64 __fastcall(CProfileTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800156a0`

## callees

- `0x1800057e0`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180014a60`
- `0x180014b90`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014abb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014abb`

## pseudocode

```c
__int64 __fastcall CProfileTask::CreateCacheObject(CProfileTask *this)
{
  void *v2; // rdx
  int v3; // ebx
  void *v4; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp+10h] BYREF

  ppv = 0;
  v3 = CObjectInGIT<CComCoCreator_Standard>::CreateInstanceAndMarshalToGIT(
         (CProfileTask *)((char *)this + 8),
         &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
         &ppv);
  if ( v3 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids,
        (unsigned int)v3);
  }
  else
  {
    v6 = 0;
    v3 = CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT((__int64)this + 48, v2, &v6);
    if ( v3 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          16,
          WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids,
          (unsigned int)v3);
    }
    else
    {
      v4 = (void *)*((_QWORD *)this + 11);
      if ( v4 )
      {
        SetEvent(v4);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x200000) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014a60  mov     [rsp+arg_10], rbx
0x180014a65  push    rdi
0x180014a66  sub     rsp, 20h
0x180014a6a  mov     rdi, rcx
0x180014a6d  mov     [rsp+28h+ppv], 0
0x180014a76  add     rcx, 8; this
0x180014a7a  lea     r8, [rsp+28h+ppv]; ppv
0x180014a7f  lea     rdx, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; struct _GUID *
0x180014a86  call    ?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_Standard@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; CObjectInGIT<CComCoCreator_Standard>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)
0x180014a8b  mov     ebx, eax
0x180014a8d  test    eax, eax
0x180014a8f  js      loc_180014B49
0x180014a95  lea     rcx, [rdi+30h]
0x180014a99  mov     [rsp+28h+arg_0], 0
0x180014aa2  lea     r8, [rsp+28h+arg_0]
0x180014aa7  call    ?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)
0x180014aac  mov     ebx, eax
0x180014aae  test    eax, eax
0x180014ab0  js      short loc_180014B05
0x180014ab2  mov     rcx, [rdi+58h]; hEvent
0x180014ab6  test    rcx, rcx
0x180014ab9  jz      short loc_180014AF2
0x180014abb  call    cs:__imp_SetEvent
0x180014ac1  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ac8  lea     rax, WPP_GLOBAL_Control
0x180014acf  cmp     rcx, rax
0x180014ad2  jz      short loc_180014AF2
0x180014ad4  test    dword ptr [rcx+1Ch], 200000h
0x180014adb  jz      short loc_180014AF2
0x180014add  mov     rcx, [rcx+10h]
0x180014ae1  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180014ae8  mov     edx, 0Fh
0x180014aed  call    WPP_SF_
0x180014af2  mov     rcx, [rsp+28h+arg_0]
0x180014af7  mov     rax, [rcx]
0x180014afa  mov     rax, [rax+10h]
0x180014afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b03  jmp     short loc_180014B36
0x180014b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b0c  lea     rax, WPP_GLOBAL_Control
0x180014b13  cmp     rcx, rax
0x180014b16  jz      short loc_180014B36
0x180014b18  test    byte ptr [rcx+1Ch], 2
0x180014b1c  jz      short loc_180014B36
0x180014b1e  mov     rcx, [rcx+10h]
0x180014b22  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180014b29  mov     edx, 10h
0x180014b2e  mov     r9d, ebx
0x180014b31  call    WPP_SF_d
0x180014b36  mov     rcx, [rsp+28h+ppv]
0x180014b3b  mov     rax, [rcx]
0x180014b3e  mov     rax, [rax+10h]
0x180014b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b47  jmp     short loc_180014B7A
0x180014b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b50  lea     rax, WPP_GLOBAL_Control
0x180014b57  cmp     rcx, rax
0x180014b5a  jz      short loc_180014B7A
0x180014b5c  test    byte ptr [rcx+1Ch], 2
0x180014b60  jz      short loc_180014B7A
0x180014b62  mov     rcx, [rcx+10h]
0x180014b66  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180014b6d  mov     edx, 11h
0x180014b72  mov     r9d, ebx
0x180014b75  call    WPP_SF_d
0x180014b7a  mov     eax, ebx
0x180014b7c  mov     rbx, [rsp+28h+arg_10]
0x180014b81  add     rsp, 20h
0x180014b85  pop     rdi
0x180014b86  retn
```
