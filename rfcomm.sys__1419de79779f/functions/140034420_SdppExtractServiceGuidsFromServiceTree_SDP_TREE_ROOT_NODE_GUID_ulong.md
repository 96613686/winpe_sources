# SdppExtractServiceGuidsFromServiceTree(_SDP_TREE_ROOT_NODE *,_GUID * *,ulong *)

- ea: `0x140034420`
- end: `0x1400344eb`
- name: `?SdppExtractServiceGuidsFromServiceTree@@YAJPEAU_SDP_TREE_ROOT_NODE@@PEAPEAU_GUID@@PEAK@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _SDP_TREE_ROOT_NODE *, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task`

## callers

- `0x14003468c`

## callees

- `0x14001fbd0`
- `0x140034420`
- `0x1400349fc`
- `0x140036754`

## pseudocode

```c
__int64 __fastcall SdppExtractServiceGuidsFromServiceTree(
        struct _SDP_TREE_ROOT_NODE *a1,
        struct _GUID **a2,
        unsigned int *a3)
{
  NTSTATUS AttributeInTree; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  SDP_NODE_DATA *p_u; // rdi
  ULONGLONG LowPart; // rax
  unsigned int v11; // ebx
  struct _GUID *Pool; // r10
  SDP_NODE_DATA *v13; // rcx
  int v14; // r11d
  SDP_NODE_DATA **v15; // rcx
  int v16; // r11d
  PSDP_NODE Attribute; // [rsp+68h] [rbp+20h] BYREF

  Attribute = 0;
  AttributeInTree = SdpFindAttributeInTree(a1, 1u, &Attribute);
  v8 = (unsigned int)AttributeInTree;
  if ( AttributeInTree >= 0 )
  {
    if ( Attribute->hdr.Type == 6 )
    {
      p_u = &Attribute->u;
      LowPart = Attribute->u.int128.LowPart;
      if ( (SDP_NODE_DATA *)p_u->int128.LowPart == p_u )
      {
        LODWORD(v8) = -1073741275;
      }
      else
      {
        v11 = 0;
        while ( (SDP_NODE_DATA *)LowPart != p_u )
        {
          if ( *(_WORD *)(LowPart + 16) != 3 )
            goto LABEL_3;
          LowPart = *(_QWORD *)LowPart;
          ++v11;
        }
        Pool = (struct _GUID *)SdppAllocatePoolEx(16LL * v11, v6, v7, v8);
        if ( Pool )
        {
          v13 = (SDP_NODE_DATA *)p_u->int128.LowPart;
          LODWORD(v8) = 0;
          v14 = 0;
          while ( v13 != p_u )
          {
            SdpNormalizeUuid(v13, &Pool[v14]);
            v13 = *v15;
            v14 = v16 + 1;
          }
          *a3 = v11;
          *a2 = Pool;
        }
        else
        {
          LODWORD(v8) = -1073741670;
        }
      }
    }
    else
    {
LABEL_3:
      LODWORD(v8) = -1073741434;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140034420  push    rbx
0x140034422  push    rsi
0x140034423  push    rdi
0x140034424  push    r14
0x140034426  sub     rsp, 28h
0x14003442a  mov     rsi, r8
0x14003442d  mov     [rsp+48h+Attribute], 0
0x140034436  mov     r14, rdx
0x140034439  lea     r8, [rsp+48h+Attribute]; Attribute
0x14003443e  mov     edx, 1; AttribId
0x140034443  call    SdpFindAttributeInTree
0x140034448  mov     r9d, eax
0x14003444b  test    eax, eax
0x14003444d  js      loc_1400344DD
0x140034453  mov     rdi, [rsp+48h+Attribute]
0x140034458  mov     eax, 6
0x14003445d  cmp     ax, [rdi+10h]
0x140034461  jz      short loc_14003446B
0x140034463  mov     r9d, 0C0000186h
0x140034469  jmp     short loc_1400344DD
0x14003446b  add     rdi, 20h ; ' '
0x14003446f  mov     rax, [rdi]
0x140034472  cmp     rax, rdi
0x140034475  jnz     short loc_14003447F
0x140034477  mov     r9d, 0C0000225h
0x14003447d  jmp     short loc_1400344DD
0x14003447f  xor     ebx, ebx
0x140034481  cmp     rax, rdi
0x140034484  jz      short loc_140034498
0x140034486  mov     ecx, 3
0x14003448b  cmp     cx, [rax+10h]
0x14003448f  jnz     short loc_140034463
0x140034491  mov     rax, [rax]
0x140034494  inc     ebx
0x140034496  jmp     short loc_140034481
0x140034498  mov     ecx, ebx
0x14003449a  shl     rcx, 4
0x14003449e  call    SdppAllocatePoolEx
0x1400344a3  mov     r10, rax
0x1400344a6  test    rax, rax
0x1400344a9  jz      short loc_1400344D7
0x1400344ab  mov     rcx, [rdi]
0x1400344ae  xor     r9d, r9d
0x1400344b1  xor     r11d, r11d
0x1400344b4  jmp     short loc_1400344CB
0x1400344b6  mov     edx, r11d
0x1400344b9  shl     rdx, 4
0x1400344bd  add     rdx, r10
0x1400344c0  call    SdpNormalizeUuid
0x1400344c5  mov     rcx, [rcx]
0x1400344c8  inc     r11d
0x1400344cb  cmp     rcx, rdi
0x1400344ce  jnz     short loc_1400344B6
0x1400344d0  mov     [rsi], ebx
0x1400344d2  mov     [r14], r10
0x1400344d5  jmp     short loc_1400344DD
0x1400344d7  mov     r9d, 0C000009Ah
0x1400344dd  mov     eax, r9d
0x1400344e0  add     rsp, 28h
0x1400344e4  pop     r14
0x1400344e6  pop     rdi
0x1400344e7  pop     rsi
0x1400344e8  pop     rbx
0x1400344e9  retn
```
