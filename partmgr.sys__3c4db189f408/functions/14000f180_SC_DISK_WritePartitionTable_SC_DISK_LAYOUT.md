# SC_DISK::WritePartitionTable(SC_DISK_LAYOUT *)

- ea: `0x14000f180`
- end: `0x14000f25d`
- name: `?WritePartitionTable@SC_DISK@@QEAAJPEAVSC_DISK_LAYOUT@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this, struct SC_DISK_LAYOUT *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x14000efb8`
- `0x14000f430`
- `0x14000f5ac`
- `0x14001d090`
- `0x14001d13c`

## callees

- `0x14000510c`
- `0x1400058a4`
- `0x14000ea44`
- `0x14000f180`
- `0x14000fc84`
- `0x140010380`

## pseudocode

```c
__int64 __fastcall SC_DISK::WritePartitionTable(SC_DISK *this, struct SC_DISK_LAYOUT *a2)
{
  int v3; // edx
  bool v5; // zf
  _CREATE_DISK v8; // [rsp+20h] [rbp-28h] BYREF
  SC_DISK *v9; // [rsp+50h] [rbp+8h] BYREF

  memset(&v8.Mbr, 0, 20);
  v3 = 0;
  if ( *((_DWORD *)this + 64) != 2
    || (v8.PartitionStyle = *(_DWORD *)a2, v3 = SC_DISK::CreatePartitionTable(this, &v8), v3 >= 0)
    && (v3 = SC_DISK::ResetPartitionCache(this), v3 >= 0) )
  {
    if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        v5 = *((_DWORD *)this + 64) == 1;
        v9 = this;
        return (unsigned int)SC_GPT::WritePartitionTable(&v9, a2, !v5);
      }
    }
    else
    {
      if ( !*((_DWORD *)this + 64)
        || *((_DWORD *)a2 + 1) == 4
        && *((_BYTE *)a2 + 80) == 0xEE
        && !*((_BYTE *)a2 + 224)
        && !*((_BYTE *)a2 + 368)
        && !*((_BYTE *)a2 + 512) )
      {
        SC_MBR::Initialize((SC_MBR *)&v9, this);
        return (unsigned int)SC_MBR::WritePartitionTable(&v9, a2);
      }
      return (unsigned int)-1073741637;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000f180  mov     [rsp+arg_8], rbx
0x14000f185  push    rdi
0x14000f186  sub     rsp, 40h
0x14000f18a  mov     rbx, rdx
0x14000f18d  mov     dword ptr [rsp+48h+var_28.4], 0
0x14000f195  xor     edx, edx
0x14000f197  xorps   xmm0, xmm0
0x14000f19a  cmp     dword ptr [rcx+100h], 2
0x14000f1a1  mov     rdi, rcx
0x14000f1a4  movups  xmmword ptr [rsp+48h+var_28.4+4], xmm0
0x14000f1a9  jnz     short loc_14000F1D3
0x14000f1ab  mov     eax, [rbx]
0x14000f1ad  lea     rdx, [rsp+48h+var_28]; struct _CREATE_DISK *
0x14000f1b2  mov     [rsp+48h+var_28.PartitionStyle], eax
0x14000f1b6  call    ?CreatePartitionTable@SC_DISK@@QEAAJPEAU_CREATE_DISK@@@Z; SC_DISK::CreatePartitionTable(_CREATE_DISK *)
0x14000f1bb  mov     edx, eax
0x14000f1bd  test    eax, eax
0x14000f1bf  js      loc_14000F24F
0x14000f1c5  mov     rcx, rdi; this
0x14000f1c8  call    ?ResetPartitionCache@SC_DISK@@QEAAJXZ; SC_DISK::ResetPartitionCache(void)
0x14000f1cd  mov     edx, eax
0x14000f1cf  test    eax, eax
0x14000f1d1  js      short loc_14000F24F
0x14000f1d3  mov     ecx, [rbx]
0x14000f1d5  test    ecx, ecx
0x14000f1d7  jz      short loc_14000F1FC
0x14000f1d9  cmp     ecx, 1
0x14000f1dc  jnz     short loc_14000F24F
0x14000f1de  cmp     [rdi+100h], ecx
0x14000f1e4  mov     rdx, rbx; struct SC_DISK_LAYOUT *
0x14000f1e7  lea     rcx, [rsp+48h+arg_0]; this
0x14000f1ec  mov     [rsp+48h+arg_0], rdi
0x14000f1f1  setnz   r8b; unsigned __int8
0x14000f1f5  call    ?WritePartitionTable@SC_GPT@@QEAAJPEAVSC_DISK_LAYOUT@@E@Z; SC_GPT::WritePartitionTable(SC_DISK_LAYOUT *,uchar)
0x14000f1fa  jmp     short loc_14000F24D
0x14000f1fc  cmp     dword ptr [rdi+100h], 0
0x14000f203  jz      short loc_14000F233
0x14000f205  cmp     dword ptr [rbx+4], 4
0x14000f209  jnz     short loc_14000F22C
0x14000f20b  cmp     byte ptr [rbx+50h], 0EEh
0x14000f20f  jnz     short loc_14000F22C
0x14000f211  cmp     byte ptr [rbx+0E0h], 0
0x14000f218  jnz     short loc_14000F22C
0x14000f21a  cmp     byte ptr [rbx+170h], 0
0x14000f221  jnz     short loc_14000F22C
0x14000f223  cmp     byte ptr [rbx+200h], 0
0x14000f22a  jz      short loc_14000F233
0x14000f22c  mov     edx, 0C00000BBh
0x14000f231  jmp     short loc_14000F24F
0x14000f233  mov     rdx, rdi; struct SC_DISK *
0x14000f236  lea     rcx, [rsp+48h+arg_0]; this
0x14000f23b  call    ?Initialize@SC_MBR@@QEAAXPEAVSC_DISK@@@Z; SC_MBR::Initialize(SC_DISK *)
0x14000f240  lea     rcx, [rsp+48h+arg_0]; this
0x14000f245  mov     rdx, rbx; struct SC_DISK_LAYOUT *
0x14000f248  call    ?WritePartitionTable@SC_MBR@@QEAAJPEAVSC_DISK_LAYOUT@@@Z; SC_MBR::WritePartitionTable(SC_DISK_LAYOUT *)
0x14000f24d  mov     edx, eax
0x14000f24f  mov     rbx, [rsp+48h+arg_8]
0x14000f254  mov     eax, edx
0x14000f256  add     rsp, 40h
0x14000f25a  pop     rdi
0x14000f25b  retn
```
