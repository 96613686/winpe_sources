# CMsftDiscFormat2Erase::WriteEngineUpdate(IDispatch *,IDispatch *)

- ea: `0x180027df0`
- end: `0x180027f78`
- name: `?WriteEngineUpdate@CMsftDiscFormat2Erase@@UEAAXPEAUIDispatch@@0@Z`
- size: `392`
- prototype: `void __fastcall(CMsftDiscFormat2Erase *__hidden this, struct IDispatch *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800140f4`
- `0x180026b20`
- `0x180027df0`
- `0x180048d4c`
- `0x18004a010`

## pseudocode

```c
void __fastcall CMsftDiscFormat2Erase::WriteEngineUpdate(
        CMsftDiscFormat2Erase *this,
        struct IDispatch *a2,
        struct IDispatch *a3)
{
  struct IDispatchVtbl *lpVtbl; // rax
  int v5; // eax
  int v6; // ebx
  unsigned int v7; // edx
  int v8; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h] BYREF
  int v10; // [rsp+58h] [rbp+20h] BYREF

  lpVtbl = a3->lpVtbl;
  v9 = 0;
  v5 = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a3,
         &GUID_27354136_7f64_5b0f_8f00_5d77afbe261e,
         &v9);
  if ( v5 >= 0 )
  {
    v10 = 0;
    v8 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 80LL))(v9, &v10);
    if ( v6 < 0 || (v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v9 + 56LL))(v9, &v8), v6 < 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          11,
          WPP_e133fdf0b0153a7a1b863863542773e4_Traceguids,
          (unsigned int)v6);
      }
    }
    else
    {
      v7 = v10 - v8;
      if ( !*((_BYTE *)this + 208) )
        v7 += *((_DWORD *)this + 50);
      Imapi2Utility::CTaskTimeEstimator::put_CompletedSteps(*((Imapi2Utility::CTaskTimeEstimator **)this + 24), v7);
      CProxy_DDiscFormat2EraseEvents<CMsftDiscFormat2Erase>::Fire_Update(
        (char *)this + 24,
        *(_DWORD *)(*((_QWORD *)this + 24) + 8LL) / 0x3E8u,
        *(_DWORD *)(*((_QWORD *)this + 24) + 4LL) / 0x3E8u);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 32),
      10,
      WPP_e133fdf0b0153a7a1b863863542773e4_Traceguids,
      (unsigned int)v5);
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
}

```

## disassembly

```asm
0x180027df0  mov     [rsp+arg_0], rbx
0x180027df5  push    rdi
0x180027df6  sub     rsp, 30h
0x180027dfa  mov     rax, [r8]
0x180027dfd  lea     rdx, _GUID_27354136_7f64_5b0f_8f00_5d77afbe261e
0x180027e04  mov     r9, r8
0x180027e07  mov     [rsp+38h+var_10], 0
0x180027e10  mov     rdi, rcx
0x180027e13  lea     r8, [rsp+38h+var_10]
0x180027e18  mov     rcx, r9
0x180027e1b  mov     rax, [rax]
0x180027e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e23  test    eax, eax
0x180027e25  jns     short loc_180027E78
0x180027e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e2e  lea     rdx, WPP_GLOBAL_Control
0x180027e35  cmp     rcx, rdx
0x180027e38  jz      loc_180027F57
0x180027e3e  test    byte ptr [rcx+10Ch], 4
0x180027e45  jz      loc_180027F57
0x180027e4b  cmp     byte ptr [rcx+109h], 3
0x180027e52  jb      loc_180027F57
0x180027e58  mov     rcx, [rcx+100h]
0x180027e5f  lea     r8, WPP_e133fdf0b0153a7a1b863863542773e4_Traceguids
0x180027e66  mov     edx, 0Ah
0x180027e6b  mov     r9d, eax
0x180027e6e  call    WPP_SF_d
0x180027e73  jmp     loc_180027F57
0x180027e78  mov     rcx, [rsp+38h+var_10]
0x180027e7d  lea     rdx, [rsp+38h+arg_18]
0x180027e82  mov     [rsp+38h+arg_18], 0
0x180027e8a  mov     [rsp+38h+var_18], 0
0x180027e92  mov     rax, [rcx]
0x180027e95  mov     rax, [rax+50h]
0x180027e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e9e  mov     ebx, eax
0x180027ea0  test    eax, eax
0x180027ea2  js      short loc_180027ED9
0x180027ea4  mov     rcx, [rsp+38h+var_10]
0x180027ea9  lea     rdx, [rsp+38h+var_18]
0x180027eae  mov     rax, [rcx]
0x180027eb1  mov     rax, [rax+38h]
0x180027eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eba  mov     ebx, eax
0x180027ebc  test    eax, eax
0x180027ebe  js      short loc_180027ED9
0x180027ec0  mov     edx, [rsp+38h+arg_18]
0x180027ec4  sub     edx, [rsp+38h+var_18]
0x180027ec8  cmp     byte ptr [rdi+0D0h], 0
0x180027ecf  jnz     short loc_180027F1F
0x180027ed1  add     edx, [rdi+0C8h]
0x180027ed7  jmp     short loc_180027F1F
0x180027ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ee0  lea     rdx, WPP_GLOBAL_Control
0x180027ee7  cmp     rcx, rdx
0x180027eea  jz      short loc_180027F19
0x180027eec  test    byte ptr [rcx+10Ch], 4
0x180027ef3  jz      short loc_180027F19
0x180027ef5  cmp     byte ptr [rcx+109h], 3
0x180027efc  jb      short loc_180027F19
0x180027efe  mov     rcx, [rcx+100h]
0x180027f05  lea     r8, WPP_e133fdf0b0153a7a1b863863542773e4_Traceguids
0x180027f0c  mov     edx, 0Bh
0x180027f11  mov     r9d, ebx
0x180027f14  call    WPP_SF_d
0x180027f19  xor     edx, edx; unsigned int
0x180027f1b  test    ebx, ebx
0x180027f1d  js      short loc_180027F57
0x180027f1f  mov     rcx, [rdi+0C0h]; this
0x180027f26  call    ?put_CompletedSteps@CTaskTimeEstimator@Imapi2Utility@@QEAAXK@Z; Imapi2Utility::CTaskTimeEstimator::put_CompletedSteps(ulong)
0x180027f2b  mov     rcx, [rdi+0C0h]
0x180027f32  mov     r9d, 10624DD3h
0x180027f38  mov     eax, r9d
0x180027f3b  mul     dword ptr [rcx+4]
0x180027f3e  mov     eax, r9d
0x180027f41  mov     r8d, edx
0x180027f44  mul     dword ptr [rcx+8]
0x180027f47  shr     r8d, 6
0x180027f4b  lea     rcx, [rdi+18h]
0x180027f4f  shr     edx, 6
0x180027f52  call    ?Fire_Update@?$CProxy_DDiscFormat2EraseEvents@VCMsftDiscFormat2Erase@@@@QEAAXJJ@Z; CProxy_DDiscFormat2EraseEvents<CMsftDiscFormat2Erase>::Fire_Update(long,long)
0x180027f57  mov     rcx, [rsp+38h+var_10]
0x180027f5c  test    rcx, rcx
0x180027f5f  jz      short loc_180027F6D
0x180027f61  mov     rax, [rcx]
0x180027f64  mov     rax, [rax+10h]
0x180027f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f6d  mov     rbx, [rsp+38h+arg_0]
0x180027f72  add     rsp, 30h
0x180027f76  pop     rdi
0x180027f77  retn
```
