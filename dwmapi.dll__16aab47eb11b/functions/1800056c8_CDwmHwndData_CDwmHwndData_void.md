# CDwmHwndData::~CDwmHwndData(void)

- ea: `0x1800056c8`
- end: `0x18000577f`
- name: `??1CDwmHwndData@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(CDwmHwndData *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005534`
- `0x180005c64`

## callees

- `0x1800056c8`
- `0x1800136ec`
- `0x180017010`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x18000570d`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x18000570d`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18000575a`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18000575a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056f2`

## pseudocode

```c
void __fastcall CDwmHwndData::~CDwmHwndData(CDwmHwndData *this)
{
  void *v2; // rcx
  struct _RTL_GENERIC_TABLE *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  void *v8; // rcx
  PVOID RestartKey; // [rsp+30h] [rbp+8h] BYREF

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    CloseHandle(v2);
  v3 = (struct _RTL_GENERIC_TABLE *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    RestartKey = 0;
    while ( 1 )
    {
      v6 = RtlEnumerateGenericTableWithoutSplaying(v3, &RestartKey);
      v7 = v6;
      if ( !v6 )
        break;
      v6[1] = 0;
      if ( !RtlIsThreadWithinLoaderCallout() )
      {
        v4 = v7[3];
        if ( v4 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
          v7[3] = 0;
        }
      }
      v5 = v7[4];
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        v7[4] = 0;
      }
      v3 = (struct _RTL_GENERIC_TABLE *)*((_QWORD *)this + 6);
    }
    v8 = (void *)*((_QWORD *)this + 6);
    if ( v8 )
      CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(v8);
  }
}

```

## disassembly

```asm
0x1800056c8  mov     [rsp+arg_8], rbx
0x1800056cd  push    rdi
0x1800056ce  sub     rsp, 20h
0x1800056d2  mov     rdi, rcx
0x1800056d5  mov     rcx, [rcx+18h]; hObject
0x1800056d9  test    rcx, rcx
0x1800056dc  jnz     short loc_1800056F2
0x1800056de  mov     rcx, [rdi+30h]
0x1800056e2  test    rcx, rcx
0x1800056e5  jnz     short loc_1800056FA
0x1800056e7  mov     rbx, [rsp+28h+arg_8]
0x1800056ec  add     rsp, 20h
0x1800056f0  pop     rdi
0x1800056f1  retn
0x1800056f2  call    cs:__imp_CloseHandle
0x1800056f8  jmp     short loc_1800056DE
0x1800056fa  mov     [rsp+28h+RestartKey], 0
0x180005703  jmp     short loc_180005755
0x180005705  mov     qword ptr [rbx+8], 0
0x18000570d  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x180005713  test    al, al
0x180005715  jnz     short loc_180005734
0x180005717  mov     rcx, [rbx+18h]
0x18000571b  test    rcx, rcx
0x18000571e  jz      short loc_180005734
0x180005720  mov     rax, [rcx]
0x180005723  mov     rax, [rax+10h]
0x180005727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572c  mov     qword ptr [rbx+18h], 0
0x180005734  mov     rcx, [rbx+20h]
0x180005738  test    rcx, rcx
0x18000573b  jz      short loc_180005751
0x18000573d  mov     rax, [rcx]
0x180005740  mov     rax, [rax+10h]
0x180005744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005749  mov     qword ptr [rbx+20h], 0
0x180005751  mov     rcx, [rdi+30h]; Table
0x180005755  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x18000575a  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180005760  mov     rbx, rax
0x180005763  test    rax, rax
0x180005766  jnz     short loc_180005705
0x180005768  mov     rcx, [rdi+30h]; void *
0x18000576c  test    rcx, rcx
0x18000576f  jz      loc_1800056E7
0x180005775  call    ??_G?$CGenericTableMap@_KVCProxySurfaceElement@@@@QEAAPEAXI@Z; CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(uint)
0x18000577a  jmp     loc_1800056E7
```
