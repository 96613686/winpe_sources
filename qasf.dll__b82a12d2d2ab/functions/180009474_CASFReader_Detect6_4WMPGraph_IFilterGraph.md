# CASFReader::Detect6_4WMPGraph(IFilterGraph *)

- ea: `0x180009474`
- end: `0x1800095a1`
- name: `?Detect6_4WMPGraph@CASFReader@@AEAAXPEAUIFilterGraph@@@Z`
- size: `301`
- prototype: `void __fastcall(CASFReader *__hidden this, struct IFilterGraph *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a8a0`

## callees

- `0x180001460`
- `0x180009474`
- `0x18001f010`

## pseudocode

```c
void __fastcall CASFReader::Detect6_4WMPGraph(CASFReader *this, struct IFilterGraph *a2)
{
  struct IFilterGraphVtbl *lpVtbl; // rax
  __int64 v4; // rcx
  __int64 v5; // [rsp+20h] [rbp-30h] BYREF
  __int64 v6; // [rsp+28h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-20h] BYREF
  __int64 v8; // [rsp+38h] [rbp-18h] BYREF

  *((_DWORD *)this + 122) = 0;
  lpVtbl = a2->lpVtbl;
  v5 = 0;
  if ( ((__int64 (__fastcall *)(struct IFilterGraph *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &IID_IObjectWithSite,
         &v5) >= 0 )
  {
    v8 = 0;
    if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v5 + 32LL))(v5, &IID_IServiceProvider, &v8) >= 0 )
    {
      v6 = 0;
      if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v5 + 32LL))(v5, &IID_IOleClientSite, &v6) >= 0 )
      {
        v7 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v6)(v6, &IID_IMediaPlayer, &v7) >= 0 )
        {
          v4 = v7;
          *((_DWORD *)this + 122) = 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
}

```

## disassembly

```asm
0x180009474  mov     [rsp-8+arg_10], rbx
0x180009479  push    rbp
0x18000947a  mov     rbp, rsp
0x18000947d  sub     rsp, 50h
0x180009481  mov     rax, cs:__security_cookie
0x180009488  xor     rax, rsp
0x18000948b  mov     [rbp+var_10], rax
0x18000948f  mov     dword ptr [rcx+1E8h], 0
0x180009499  lea     r8, [rbp+var_30]
0x18000949d  mov     rax, [rdx]
0x1800094a0  mov     r9, rdx
0x1800094a3  mov     rbx, rcx
0x1800094a6  mov     [rbp+var_30], 0
0x1800094ae  lea     rdx, IID_IObjectWithSite
0x1800094b5  mov     rcx, r9
0x1800094b8  mov     rax, [rax]
0x1800094bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c0  test    eax, eax
0x1800094c2  js      loc_18000958A
0x1800094c8  mov     rcx, [rbp+var_30]
0x1800094cc  lea     r8, [rbp+var_18]
0x1800094d0  mov     [rbp+var_18], 0
0x1800094d8  lea     rdx, IID_IServiceProvider
0x1800094df  mov     rax, [rcx]
0x1800094e2  mov     rax, [rax+20h]
0x1800094e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094eb  test    eax, eax
0x1800094ed  js      loc_18000957A
0x1800094f3  mov     rcx, [rbp+var_30]
0x1800094f7  lea     r8, [rbp+var_28]
0x1800094fb  mov     [rbp+var_28], 0
0x180009503  lea     rdx, IID_IOleClientSite
0x18000950a  mov     rax, [rcx]
0x18000950d  mov     rax, [rax+20h]
0x180009511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009516  test    eax, eax
0x180009518  js      short loc_18000956A
0x18000951a  mov     rcx, [rbp+var_28]
0x18000951e  lea     r8, [rbp+var_20]
0x180009522  mov     [rbp+var_20], 0
0x18000952a  lea     rdx, IID_IMediaPlayer
0x180009531  mov     rax, [rcx]
0x180009534  mov     rax, [rax]
0x180009537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000953c  test    eax, eax
0x18000953e  js      short loc_18000955A
0x180009540  mov     rcx, [rbp+var_20]
0x180009544  mov     dword ptr [rbx+1E8h], 1
0x18000954e  mov     rax, [rcx]
0x180009551  mov     rax, [rax+10h]
0x180009555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955a  mov     rcx, [rbp+var_28]
0x18000955e  mov     rax, [rcx]
0x180009561  mov     rax, [rax+10h]
0x180009565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956a  mov     rcx, [rbp+var_18]
0x18000956e  mov     rax, [rcx]
0x180009571  mov     rax, [rax+10h]
0x180009575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957a  mov     rcx, [rbp+var_30]
0x18000957e  mov     rax, [rcx]
0x180009581  mov     rax, [rax+10h]
0x180009585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958a  mov     rcx, [rbp+var_10]
0x18000958e  xor     rcx, rsp; StackCookie
0x180009591  call    __security_check_cookie
0x180009596  mov     rbx, [rsp+50h+arg_10]
0x18000959b  add     rsp, 50h
0x18000959f  pop     rbp
0x1800095a0  retn
```
