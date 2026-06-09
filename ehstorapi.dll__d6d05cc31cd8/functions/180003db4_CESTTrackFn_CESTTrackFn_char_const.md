# CESTTrackFn::CESTTrackFn(char const *)

- ea: `0x180003db4`
- end: `0x180003dea`
- name: `??0CESTTrackFn@@QEAA@PEBD@Z`
- size: `54`
- prototype: `CESTTrackFn *(CESTTrackFn *__hidden this, const char *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f64`
- `0x1800042f4`
- `0x180005d50`
- `0x180006400`
- `0x180006a64`
- `0x1800071c0`

## callees

- `0x180003db4`
- `0x180005fd4`

## pseudocode

```c
CESTTrackFn *__fastcall CESTTrackFn::CESTTrackFn(CESTTrackFn *this, char *a2)
{
  CESTTrackFn *v2; // r10

  *((_QWORD *)this + 33) = 0;
  v2 = this;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 65);
    StringCbCopyA((char *)this, (__int64)a2, a2);
  }
  return v2;
}

```

## disassembly

```asm
0x180003db4  sub     rsp, 28h
0x180003db8  mov     qword ptr [rcx+108h], 0
0x180003dc3  mov     r10, rcx
0x180003dc6  mov     rax, cs:WPP_GLOBAL_Control
0x180003dcd  test    byte ptr [rax+1Ch], 10h
0x180003dd1  jz      short loc_180003DE2
0x180003dd3  lock inc dword ptr [rcx+104h]
0x180003dda  mov     r8, rdx; char *
0x180003ddd  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180003de2  mov     rax, r10
0x180003de5  add     rsp, 28h
0x180003de9  retn
```
