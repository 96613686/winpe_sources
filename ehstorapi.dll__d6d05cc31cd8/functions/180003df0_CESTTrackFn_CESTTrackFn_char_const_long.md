# CESTTrackFn::CESTTrackFn(char const *,long *)

- ea: `0x180003df0`
- end: `0x180003e22`
- name: `??0CESTTrackFn@@QEAA@PEBDPEAJ@Z`
- size: `50`
- prototype: `CESTTrackFn *(CESTTrackFn *__hidden this, const char *, int *)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180004380`
- `0x1800046b4`
- `0x180004a60`
- `0x18000521c`
- `0x180005960`
- `0x18000664c`
- `0x180006af0`
- `0x180007090`
- `0x180007290`
- `0x180007430`
- `0x180007840`
- `0x1800079d0`
- `0x180007f00`
- `0x1800082b0`

## callees

- `0x180003df0`
- `0x180005fd4`

## pseudocode

```c
CESTTrackFn *__fastcall CESTTrackFn::CESTTrackFn(CESTTrackFn *this, char *a2, int *a3)
{
  CESTTrackFn *v3; // r10

  *((_QWORD *)this + 33) = a3;
  v3 = this;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 65);
    StringCbCopyA((char *)this, (__int64)a2, a2);
  }
  return v3;
}

```

## disassembly

```asm
0x180003df0  sub     rsp, 28h
0x180003df4  mov     [rcx+108h], r8
0x180003dfb  mov     r10, rcx
0x180003dfe  mov     rax, cs:WPP_GLOBAL_Control
0x180003e05  test    byte ptr [rax+1Ch], 10h
0x180003e09  jz      short loc_180003E1A
0x180003e0b  lock inc dword ptr [rcx+104h]
0x180003e12  mov     r8, rdx; char *
0x180003e15  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180003e1a  mov     rax, r10
0x180003e1d  add     rsp, 28h
0x180003e21  retn
```
