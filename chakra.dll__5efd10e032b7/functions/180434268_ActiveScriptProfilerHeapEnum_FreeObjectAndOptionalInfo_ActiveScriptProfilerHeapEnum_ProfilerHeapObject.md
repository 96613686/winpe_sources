# ActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo(ActiveScriptProfilerHeapEnum::ProfilerHeapObject *)

- ea: `0x180434268`
- end: `0x18043431b`
- name: `?FreeObjectAndOptionalInfo@ActiveScriptProfilerHeapEnum@@AEAAXPEAUProfilerHeapObject@1@@Z`
- size: `179`
- prototype: `void(ActiveScriptProfilerHeapEnum *__hidden this, struct ActiveScriptProfilerHeapEnum::ProfilerHeapObject *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1803f7b74`
- `0x180431ad8`
- `0x180434330`

## callees

- `0x1804341d4`
- `0x180434268`
- `0x1804348fc`
- `0x1804350f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804342c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804342f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804342c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804342f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18043430f`

## pseudocode

```c
void __fastcall ActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo(
        ActiveScriptProfilerHeapEnum *this,
        struct ActiveScriptProfilerHeapEnum::ProfilerHeapObject *a2)
{
  unsigned __int16 v3; // si
  struct ProfilerHeapObjectOptionalInfo *NextOptionalInfo; // rdi

  if ( (*((_BYTE *)this + 468) & 2) != 0 )
  {
    v3 = ActiveScriptProfilerHeapEnum::ProfilerHeapObject::OptionalInfoCountJSOnly(a2);
    if ( v3 )
    {
      NextOptionalInfo = (struct ActiveScriptProfilerHeapEnum::ProfilerHeapObject *)((char *)a2 + 40);
      if ( a2 != (struct ActiveScriptProfilerHeapEnum::ProfilerHeapObject *)-40LL )
      {
        do
        {
          if ( !v3 )
            break;
          --v3;
          if ( *(_DWORD *)NextOptionalInfo == 4 && *((_WORD *)NextOptionalInfo + 6) == 6 )
            CoTaskMemFree(*((LPVOID *)NextOptionalInfo + 2));
          NextOptionalInfo = ActiveScriptProfilerHeapEnum::GetNextOptionalInfo(this, NextOptionalInfo);
        }
        while ( NextOptionalInfo );
      }
    }
  }
  if ( *(_QWORD *)a2 )
  {
    ActiveScriptProfilerHeapEnum::FreeHostObjectExternalObjectList(this, *(struct HostProfilerHeapObject **)a2);
    CoTaskMemFree(*(LPVOID *)a2);
    *(_QWORD *)a2 = 0;
  }
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x180434268  mov     r11, rsp
0x18043426b  mov     [r11+18h], rbx
0x18043426f  mov     [r11+10h], rdx
0x180434273  mov     [r11+8], rcx
0x180434277  push    rbp
0x180434278  push    rsi
0x180434279  push    rdi
0x18043427a  sub     rsp, 20h
0x18043427e  mov     rax, rcx
0x180434281  xor     ebp, ebp
0x180434283  mov     rbx, rdx
0x180434286  test    byte ptr [rax+1D4h], 2
0x18043428d  jz      short loc_1804342E1
0x18043428f  mov     rcx, rdx; this
0x180434292  call    ?OptionalInfoCountJSOnly@ProfilerHeapObject@ActiveScriptProfilerHeapEnum@@QEAAGXZ; ActiveScriptProfilerHeapEnum::ProfilerHeapObject::OptionalInfoCountJSOnly(void)
0x180434297  movzx   esi, ax
0x18043429a  test    ax, ax
0x18043429d  jz      short loc_1804342E1
0x18043429f  lea     rdi, [rbx+28h]
0x1804342a3  test    rdi, rdi
0x1804342a6  jz      short loc_1804342E1
0x1804342a8  test    si, si
0x1804342ab  jz      short loc_1804342E1
0x1804342ad  mov     eax, 0FFFFh
0x1804342b2  add     si, ax
0x1804342b5  cmp     dword ptr [rdi], 4
0x1804342b8  jnz     short loc_1804342D1
0x1804342ba  cmp     word ptr [rdi+0Ch], 6
0x1804342bf  jnz     short loc_1804342D1
0x1804342c1  mov     rcx, [rdi+10h]; pv
0x1804342c5  call    cs:__imp_CoTaskMemFree
0x1804342cc  nop     dword ptr [rax+rax+00h]
0x1804342d1  mov     rdx, rdi; struct ProfilerHeapObjectOptionalInfo *
0x1804342d4  call    ?GetNextOptionalInfo@ActiveScriptProfilerHeapEnum@@AEAAPEAUProfilerHeapObjectOptionalInfo@@PEAU2@@Z; ActiveScriptProfilerHeapEnum::GetNextOptionalInfo(ProfilerHeapObjectOptionalInfo *)
0x1804342d9  mov     rdi, rax
0x1804342dc  test    rax, rax
0x1804342df  jnz     short loc_1804342A8
0x1804342e1  mov     rdx, [rbx]; struct HostProfilerHeapObject *
0x1804342e4  test    rdx, rdx
0x1804342e7  jz      short loc_180434300
0x1804342e9  call    ?FreeHostObjectExternalObjectList@ActiveScriptProfilerHeapEnum@@AEAAXAEAUHostProfilerHeapObject@@@Z; ActiveScriptProfilerHeapEnum::FreeHostObjectExternalObjectList(HostProfilerHeapObject &)
0x1804342ee  mov     rcx, [rbx]; pv
0x1804342f1  call    cs:__imp_CoTaskMemFree
0x1804342f8  nop     dword ptr [rax+rax+00h]
0x1804342fd  mov     [rbx], rbp
0x180434300  mov     rcx, rbx
0x180434303  mov     rbx, [rsp+38h+arg_10]
0x180434308  add     rsp, 20h
0x18043430c  pop     rdi
0x18043430d  pop     rsi
0x18043430e  pop     rbp
0x18043430f  jmp     cs:__imp_CoTaskMemFree
```
