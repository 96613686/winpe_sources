# SC_DISK::CreatePartitionTable(_CREATE_DISK *)

- ea: `0x14000ea44`
- end: `0x14000eb0c`
- name: `?CreatePartitionTable@SC_DISK@@QEAAJPEAU_CREATE_DISK@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this, struct _CREATE_DISK *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14000f180`
- `0x14000f7f8`
- `0x14001ced4`

## callees

- `0x1400058a4`
- `0x14000ea44`
- `0x14000fbd4`
- `0x140010380`
- `0x140010a30`
- `0x140010f20`
- `0x140011440`

## pseudocode

```c
__int64 __fastcall SC_DISK::CreatePartitionTable(SC_DISK *this, struct _CREATE_DISK *a2)
{
  __int128 v4; // xmm0
  DWORD MaxPartitionCount; // eax
  SC_DISK *v6[2]; // [rsp+20h] [rbp-89h] BYREF
  _QWORD v7[24]; // [rsp+30h] [rbp-79h] BYREF

  if ( a2 )
  {
    if ( a2->PartitionStyle == PARTITION_STYLE_MBR )
    {
      SC_MBR::Initialize((SC_MBR *)v6, this);
      return SC_MBR::CreatePartitionTable((SC_MBR *)v6, a2);
    }
    if ( a2->PartitionStyle == PARTITION_STYLE_GPT )
    {
      v6[0] = this;
      memset(v7, 0, sizeof(v7));
      v4 = *(_OWORD *)&a2->Mbr.Signature;
      MaxPartitionCount = a2->Gpt.MaxPartitionCount;
      v7[0] = 1;
      LODWORD(v7[5]) = MaxPartitionCount;
      *(_OWORD *)&v7[1] = v4;
      return SC_GPT::WritePartitionTable(v6, (struct SC_DISK_LAYOUT *)v7, 1);
    }
    if ( a2->PartitionStyle != PARTITION_STYLE_RAW )
      return 3221225659LL;
  }
  v6[0] = this;
  return SC_RAW::CreatePartitionTable((SC_RAW *)v6);
}

```

## disassembly

```asm
0x14000ea44  mov     [rsp-8+arg_10], rbx
0x14000ea49  push    rbp
0x14000ea4a  lea     rbp, [rsp-57h]
0x14000ea4f  sub     rsp, 100h
0x14000ea56  mov     rax, cs:__security_cookie
0x14000ea5d  xor     rax, rsp
0x14000ea60  mov     [rbp+57h+var_10], rax
0x14000ea64  mov     rbx, rdx
0x14000ea67  mov     rdx, rcx; struct SC_DISK *
0x14000ea6a  test    rbx, rbx
0x14000ea6d  jz      short loc_14000EADF
0x14000ea6f  mov     ecx, [rbx]
0x14000ea71  test    ecx, ecx
0x14000ea73  jz      short loc_14000EAC6
0x14000ea75  sub     ecx, 1
0x14000ea78  jz      short loc_14000EA86
0x14000ea7a  cmp     ecx, 1
0x14000ea7d  jz      short loc_14000EADF
0x14000ea7f  mov     eax, 0C00000BBh
0x14000ea84  jmp     short loc_14000EAEE
0x14000ea86  mov     [rsp+100h+var_E0], rdx
0x14000ea8b  lea     rcx, [rbp+57h+var_D0]; void *
0x14000ea8f  xor     edx, edx; Val
0x14000ea91  mov     r8d, 0C0h; Size
0x14000ea97  call    memset
0x14000ea9c  movups  xmm0, xmmword ptr [rbx+4]
0x14000eaa0  mov     eax, [rbx+14h]
0x14000eaa3  lea     rdx, [rbp+57h+var_D0]; struct SC_DISK_LAYOUT *
0x14000eaa7  mov     r8b, 1; unsigned __int8
0x14000eaaa  mov     [rbp+57h+var_D0], 1
0x14000eab2  lea     rcx, [rsp+100h+var_E0]; this
0x14000eab7  mov     [rbp+57h+var_A8], eax
0x14000eaba  movdqu  [rbp+57h+var_C8], xmm0
0x14000eabf  call    ?WritePartitionTable@SC_GPT@@QEAAJPEAVSC_DISK_LAYOUT@@E@Z; SC_GPT::WritePartitionTable(SC_DISK_LAYOUT *,uchar)
0x14000eac4  jmp     short loc_14000EAEE
0x14000eac6  lea     rcx, [rsp+100h+var_E0]; this
0x14000eacb  call    ?Initialize@SC_MBR@@QEAAXPEAVSC_DISK@@@Z; SC_MBR::Initialize(SC_DISK *)
0x14000ead0  lea     rcx, [rsp+100h+var_E0]; this
0x14000ead5  mov     rdx, rbx; struct _CREATE_DISK *
0x14000ead8  call    ?CreatePartitionTable@SC_MBR@@QEAAJPEAU_CREATE_DISK@@@Z; SC_MBR::CreatePartitionTable(_CREATE_DISK *)
0x14000eadd  jmp     short loc_14000EAEE
0x14000eadf  lea     rcx, [rsp+100h+var_E0]; this
0x14000eae4  mov     [rsp+100h+var_E0], rdx
0x14000eae9  call    ?CreatePartitionTable@SC_RAW@@QEAAJXZ; SC_RAW::CreatePartitionTable(void)
0x14000eaee  mov     rcx, [rbp+57h+var_10]
0x14000eaf2  xor     rcx, rsp; StackCookie
0x14000eaf5  call    __security_check_cookie
0x14000eafa  mov     rbx, [rsp+100h+arg_10]
0x14000eb02  add     rsp, 100h
0x14000eb09  pop     rbp
0x14000eb0a  retn
```
