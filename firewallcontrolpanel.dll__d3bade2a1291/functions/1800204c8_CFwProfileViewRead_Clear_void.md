# CFwProfileViewRead::Clear(void)

- ea: `0x1800204c8`
- end: `0x18002058f`
- name: `?Clear@CFwProfileViewRead@@QEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(DirectUI::Element **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000dee0`

## callees

- `0x1800096a8`
- `0x18000994c`
- `0x1800204c8`

## import_xrefs

- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800204dd`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800204dd`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020526`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180020526`

## pseudocode

```c
__int64 __fastcall CFwProfileViewRead::Clear(DirectUI::Element **this)
{
  int v2; // edi
  CFwCplLua *v3; // rcx
  __int64 v4; // rdx

  v2 = DirectUI::Element::Remove(this[3], this[4]);
  if ( v2 >= 0 )
  {
    v2 = DirectUI::Element::Destroy(this[4], 1);
    if ( v2 >= 0 )
    {
      CRefObject::Release(this[5]);
      this[5] = 0;
      this[3] = 0;
      this[4] = 0;
      this[7] = 0;
      *((_DWORD *)this + 12) = 0;
      return (unsigned int)v2;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 16;
      goto LABEL_5;
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 15;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids, (unsigned int)v2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800204c8  mov     [rsp+arg_0], rbx
0x1800204cd  push    rdi
0x1800204ce  sub     rsp, 20h
0x1800204d2  mov     rdx, [rcx+20h]
0x1800204d6  mov     rbx, rcx
0x1800204d9  mov     rcx, [rcx+18h]
0x1800204dd  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x1800204e3  mov     edi, eax
0x1800204e5  test    eax, eax
0x1800204e7  jns     short loc_180020520
0x1800204e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204f0  lea     rax, WPP_GLOBAL_Control
0x1800204f7  cmp     rcx, rax
0x1800204fa  jz      loc_180020582
0x180020500  test    byte ptr [rcx+1Ch], 1
0x180020504  jz      short loc_180020582
0x180020506  mov     edx, 0Fh
0x18002050b  mov     rcx, [rcx+10h]
0x18002050f  lea     r8, WPP_1c1acaf9970437da4443a5c2f4f2d84c_Traceguids
0x180020516  mov     r9d, edi
0x180020519  call    WPP_SF_d
0x18002051e  jmp     short loc_180020582
0x180020520  mov     rcx, [rbx+20h]
0x180020524  mov     dl, 1
0x180020526  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18002052c  mov     edi, eax
0x18002052e  test    eax, eax
0x180020530  jns     short loc_180020552
0x180020532  mov     rcx, cs:WPP_GLOBAL_Control
0x180020539  lea     rax, WPP_GLOBAL_Control
0x180020540  cmp     rcx, rax
0x180020543  jz      short loc_180020582
0x180020545  test    byte ptr [rcx+1Ch], 1
0x180020549  jz      short loc_180020582
0x18002054b  mov     edx, 10h
0x180020550  jmp     short loc_18002050B
0x180020552  mov     rcx, [rbx+28h]; this
0x180020556  call    ?Release@CRefObject@@QEAAKXZ; CRefObject::Release(void)
0x18002055b  mov     qword ptr [rbx+28h], 0
0x180020563  mov     qword ptr [rbx+18h], 0
0x18002056b  mov     qword ptr [rbx+20h], 0
0x180020573  mov     qword ptr [rbx+38h], 0
0x18002057b  mov     dword ptr [rbx+30h], 0
0x180020582  mov     rbx, [rsp+28h+arg_0]
0x180020587  mov     eax, edi
0x180020589  add     rsp, 20h
0x18002058d  pop     rdi
0x18002058e  retn
```
