# ResourceCache::GetResourceEntry(ResourceCache::ResourceEntry,ResourceCache::ResourceType,ResourceCache::_resourceDefinition const * &)

- ea: `0x18000b6d4`
- end: `0x18000b7f3`
- name: `?GetResourceEntry@ResourceCache@@CAJW4ResourceEntry@1@W4ResourceType@1@AEAPEBU_resourceDefinition@1@@Z`
- size: `287`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b484`
- `0x18000b694`
- `0x18000b7fc`

## callees

- `0x180008630`
- `0x18000b6d4`
- `0x18000b980`

## pseudocode

```c
__int64 __fastcall ResourceCache::GetResourceEntry(
        int a1,
        int a2,
        struct ResourceCache::_resourceDefinition near ***a3)
{
  unsigned int v3; // ebx
  bool v4; // zf
  __int64 v5; // rcx
  __int64 v6; // rdx
  struct ResourceCache::_resourceDefinition near **v7; // rcx

  v3 = 0;
  v4 = ResourceCache::s_hResourceInstance == 0;
  *a3 = 0;
  if ( v4 )
  {
    v3 = -2147221497;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v6 = 19;
LABEL_19:
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids, v3);
    }
  }
  else if ( (unsigned __int64)a1 >= 7 || a1 < 0 )
  {
    v3 = -2147024809;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v6 = 20;
      goto LABEL_19;
    }
  }
  else
  {
    v7 = &ResourceCache::s_resourceDefs + 3 * a1;
    if ( *(_DWORD *)v7 == a2 )
    {
      if ( *((_BYTE *)v7 + 9) )
      {
        *a3 = v7;
      }
      else
      {
        v3 = -2146893807;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          WPP_SF_dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            22,
            WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids,
            *((unsigned int *)v7 + 1),
            -2146893807);
      }
    }
    else
    {
      v3 = -2146893814;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v6 = 21;
        goto LABEL_19;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000b6d4  push    rbx
0x18000b6d6  sub     rsp, 30h
0x18000b6da  xor     ebx, ebx
0x18000b6dc  cmp     cs:?s_hResourceInstance@ResourceCache@@0PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * ResourceCache::s_hResourceInstance
0x18000b6e3  mov     [r8], rbx
0x18000b6e6  jnz     short loc_18000B718
0x18000b6e8  mov     ebx, 80040007h
0x18000b6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6f4  lea     rax, WPP_GLOBAL_Control
0x18000b6fb  cmp     rcx, rax
0x18000b6fe  jz      loc_18000B7EB
0x18000b704  cmp     byte ptr [rcx+19h], 2
0x18000b708  jb      loc_18000B7EB
0x18000b70e  mov     edx, 13h
0x18000b713  jmp     loc_18000B7D8
0x18000b718  movsxd  rax, ecx
0x18000b71b  cmp     rax, 7
0x18000b71f  jnb     loc_18000B7B5
0x18000b725  test    ecx, ecx
0x18000b727  js      loc_18000B7B5
0x18000b72d  lea     rax, [rax+rax*2]
0x18000b731  lea     rcx, ?s_resourceDefs@ResourceCache@@0PAU_resourceDefinition@1@A; ResourceCache::_resourceDefinition near * ResourceCache::s_resourceDefs
0x18000b738  lea     rcx, [rcx+rax*8]
0x18000b73c  cmp     [rcx], edx
0x18000b73e  jz      short loc_18000B76D
0x18000b740  mov     ebx, 8009000Ah
0x18000b745  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b74c  lea     rax, WPP_GLOBAL_Control
0x18000b753  cmp     rcx, rax
0x18000b756  jz      loc_18000B7EB
0x18000b75c  cmp     byte ptr [rcx+19h], 2
0x18000b760  jb      loc_18000B7EB
0x18000b766  mov     edx, 15h
0x18000b76b  jmp     short loc_18000B7D8
0x18000b76d  cmp     [rcx+9], bl
0x18000b770  jnz     short loc_18000B7B0
0x18000b772  mov     ebx, 80090011h
0x18000b777  mov     r10, cs:WPP_GLOBAL_Control
0x18000b77e  lea     rax, WPP_GLOBAL_Control
0x18000b785  cmp     r10, rax
0x18000b788  jz      short loc_18000B7EB
0x18000b78a  cmp     byte ptr [r10+19h], 2
0x18000b78f  jb      short loc_18000B7EB
0x18000b791  mov     r9d, [rcx+4]
0x18000b795  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x18000b79c  mov     rcx, [r10+10h]
0x18000b7a0  mov     edx, 16h
0x18000b7a5  mov     [rsp+38h+var_18], ebx
0x18000b7a9  call    WPP_SF_dd
0x18000b7ae  jmp     short loc_18000B7EB
0x18000b7b0  mov     [r8], rcx
0x18000b7b3  jmp     short loc_18000B7EB
0x18000b7b5  mov     ebx, 80070057h
0x18000b7ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7c1  lea     rax, WPP_GLOBAL_Control
0x18000b7c8  cmp     rcx, rax
0x18000b7cb  jz      short loc_18000B7EB
0x18000b7cd  cmp     byte ptr [rcx+19h], 2
0x18000b7d1  jb      short loc_18000B7EB
0x18000b7d3  mov     edx, 14h
0x18000b7d8  mov     rcx, [rcx+10h]
0x18000b7dc  lea     r8, WPP_5c28ceec2ee93c487a67b873b87d96bc_Traceguids
0x18000b7e3  mov     r9d, ebx
0x18000b7e6  call    WPP_SF_d
0x18000b7eb  mov     eax, ebx
0x18000b7ed  add     rsp, 30h
0x18000b7f1  pop     rbx
0x18000b7f2  retn
```
