# DhcpJetPrepareSearch

- ea: `0x18000ee78`
- end: `0x18000ef7e`
- name: `DhcpJetPrepareSearch`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800068b8`
- `0x180009cb0`
- `0x18000a090`
- `0x18000a410`
- `0x18000a7f0`
- `0x18004a518`
- `0x18004f128`
- `0x180050708`

## callees

- `0x18000ee78`
- `0x18000f144`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x18000eeac`
- `ESENT!JetSetCurrentIndex` at `0x18000eeac`
- `ESENT!JetMakeKey` at `0x18000ef16`
- `ESENT!JetMakeKey` at `0x18000ef16`
- `ESENT!JetSeek` at `0x18000ef4a`
- `ESENT!JetSeek` at `0x18000ef4a`
- `ESENT!JetMove` at `0x18000eefa`
- `ESENT!JetMove` at `0x18000eefa`

## string_xrefs

- `0x18000ef56`: `PrepareSearch:Move/Seek`

## pseudocode

```c
__int64 __fastcall DhcpJetPrepareSearch(__int64 a1, int a2, const void *a3, unsigned int a4)
{
  unsigned int Key; // edi
  unsigned int v9; // esi
  unsigned int v11; // eax

  Key = JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a1);
  v9 = DhcpMapJetError(Key, "PrepareSearch:SetCurrentIndex");
  if ( v9 )
    goto LABEL_2;
  if ( a2 )
  {
    v11 = JetMove(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 0x80000000, 0);
  }
  else
  {
    Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a3, a4, 1u);
    v9 = DhcpMapJetError(Key, "PrepareSearch:MakeKey");
    if ( v9 )
    {
LABEL_2:
      DhcpMapJetError(Key, a1);
      return v9;
    }
    v11 = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 0x10u);
  }
  return DhcpMapJetError(v11, "PrepareSearch:Move/Seek");
}

```

## disassembly

```asm
0x18000ee78  mov     [rsp+arg_0], rbx
0x18000ee7d  mov     [rsp+arg_8], rbp
0x18000ee82  mov     [rsp+arg_10], rsi
0x18000ee87  push    rdi
0x18000ee88  push    r14
0x18000ee8a  push    r15
0x18000ee8c  sub     rsp, 30h
0x18000ee90  mov     r15, r8
0x18000ee93  mov     ebp, edx
0x18000ee95  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000ee9c  mov     r8, rcx
0x18000ee9f  mov     rbx, rcx
0x18000eea2  mov     r14d, r9d
0x18000eea5  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000eeac  call    cs:__imp_JetSetCurrentIndex
0x18000eeb3  nop     dword ptr [rax+rax+00h]
0x18000eeb8  mov     ecx, eax
0x18000eeba  lea     rdx, aPreparesearchS; "PrepareSearch:SetCurrentIndex"
0x18000eec1  mov     edi, eax
0x18000eec3  call    DhcpMapJetError
0x18000eec8  mov     esi, eax
0x18000eeca  test    eax, eax
0x18000eecc  jz      short loc_18000EEDF
0x18000eece  mov     rdx, rbx
0x18000eed1  mov     ecx, edi
0x18000eed3  call    DhcpMapJetError
0x18000eed8  mov     eax, esi
0x18000eeda  jmp     loc_18000EF64
0x18000eedf  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000eee6  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000eeed  test    ebp, ebp
0x18000eeef  jz      short loc_18000EF08
0x18000eef1  xor     r9d, r9d; grbit
0x18000eef4  mov     r8d, 80000000h; cRow
0x18000eefa  call    cs:__imp_JetMove
0x18000ef01  nop     dword ptr [rax+rax+00h]
0x18000ef06  jmp     short loc_18000EF56
0x18000ef08  mov     r9d, r14d; cbData
0x18000ef0b  mov     [rsp+48h+grbit], 1; grbit
0x18000ef13  mov     r8, r15; pvData
0x18000ef16  call    cs:__imp_JetMakeKey
0x18000ef1d  nop     dword ptr [rax+rax+00h]
0x18000ef22  mov     ecx, eax
0x18000ef24  lea     rdx, aPreparesearchM; "PrepareSearch:MakeKey"
0x18000ef2b  mov     edi, eax
0x18000ef2d  call    DhcpMapJetError
0x18000ef32  mov     esi, eax
0x18000ef34  test    eax, eax
0x18000ef36  jnz     short loc_18000EECE
0x18000ef38  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000ef3f  lea     r8d, [rax+10h]; grbit
0x18000ef43  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000ef4a  call    cs:__imp_JetSeek
0x18000ef51  nop     dword ptr [rax+rax+00h]
0x18000ef56  lea     rdx, aPreparesearchM_0; "PrepareSearch:Move/Seek"
0x18000ef5d  mov     ecx, eax
0x18000ef5f  call    DhcpMapJetError
0x18000ef64  mov     rbx, [rsp+48h+arg_0]
0x18000ef69  mov     rbp, [rsp+48h+arg_8]
0x18000ef6e  mov     rsi, [rsp+48h+arg_10]
0x18000ef73  add     rsp, 30h
0x18000ef77  pop     r15
0x18000ef79  pop     r14
0x18000ef7b  pop     rdi
0x18000ef7c  retn
```
