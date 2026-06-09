# CComponentData::AddMenuItems(IDataObject *,IContextMenuCallback *,long *)

- ea: `0x1800053c0`
- end: `0x1800054b0`
- name: `?AddMenuItems@CComponentData@@UEAAJPEAUIDataObject@@PEAUIContextMenuCallback@@PEAJ@Z`
- size: `240`
- prototype: `int(CComponentData *__hidden this, struct IDataObject *, struct IContextMenuCallback *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800053c0`
- `0x180007140`
- `0x180008a6c`
- `0x18001eb38`
- `0x18001f638`

## pseudocode

```c
struct CDataObject *__fastcall CComponentData::AddMenuItems(
        CComponentData *this,
        struct IDataObject *a2,
        struct IContextMenuCallback *a3,
        unsigned int *a4)
{
  struct CDataObject *result; // rax
  int v8; // edx
  CComponentData *v9; // rcx
  enum _DATA_OBJECT_TYPES v10; // r9d
  CComponentData *v11; // rcx
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // edi
  struct tagCMENUITEM near **v15; // rbx

  result = ExtractOwnDataObject(a2);
  if ( result )
  {
    v8 = 0;
    if ( *((_DWORD *)result + 6) == 0x8000 )
    {
      v11 = (CComponentData *)((char *)this - 24);
      if ( !*((_DWORD *)result + 7) )
      {
        if ( (*((_BYTE *)v11 + 56) & 0x10) != 0 )
        {
          v12 = (int)s_acmiExtensionRootFolder;
          v13 = 1;
        }
        else
        {
          v12 = s_acmiRootFolder;
          v13 = 0;
        }
        if ( v12 )
        {
          v14 = *a4;
          v15 = &s_acmiExtensionRootFolder;
          if ( !v13 )
            v15 = (struct tagCMENUITEM near **)&s_acmiRootFolder;
          do
          {
            if ( v8 < 0 )
              break;
            if ( (v14 & *((_DWORD *)v15 + 3)) != 0 )
              v8 = AddCMenuItem(a3, (struct tagCMENUITEM *)v15);
            v15 = (struct tagCMENUITEM near **)((char *)v15 + 28);
          }
          while ( *(_DWORD *)v15 );
        }
        return (struct CDataObject *)(unsigned int)v8;
      }
      CComponentData::_UpdateCMenuItems(v11, *((struct CLogInfo **)result + 2));
      v10 = CCT_SCOPE;
    }
    else
    {
      if ( *((_DWORD *)result + 6) != 32769 || *((_DWORD *)result + 7) != 1 )
        return (struct CDataObject *)(unsigned int)v8;
      CComponentData::_UpdateCMenuItems((CComponentData *)((char *)this - 24), *((struct CLogInfo **)result + 2));
      v10 = CCT_RESULT;
    }
    v8 = CComponentData::_AddChildFolderContextMenuItems(v9, a3, *a4, v10);
    return (struct CDataObject *)(unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800053c0  mov     [rsp+arg_0], rbx
0x1800053c5  mov     [rsp+arg_8], rsi
0x1800053ca  push    rdi
0x1800053cb  sub     rsp, 20h
0x1800053cf  mov     rbx, rcx
0x1800053d2  mov     rdi, r9
0x1800053d5  mov     rcx, rdx; struct IDataObject *
0x1800053d8  mov     rsi, r8
0x1800053db  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x1800053e0  mov     r10, rax
0x1800053e3  test    rax, rax
0x1800053e6  jz      loc_1800054A0
0x1800053ec  mov     ecx, [rax+18h]
0x1800053ef  xor     edx, edx
0x1800053f1  sub     ecx, 8000h
0x1800053f7  jz      short loc_180005423
0x1800053f9  cmp     ecx, 1
0x1800053fc  jnz     loc_18000549E
0x180005402  mov     eax, ecx
0x180005404  cmp     [r10+1Ch], eax
0x180005408  jnz     loc_18000549E
0x18000540e  mov     rdx, [r10+10h]; struct CLogInfo *
0x180005412  lea     rcx, [rbx-18h]; this
0x180005416  call    ?_UpdateCMenuItems@CComponentData@@AEAAXPEAVCLogInfo@@@Z; CComponentData::_UpdateCMenuItems(CLogInfo *)
0x18000541b  mov     r9d, 8001h
0x180005421  jmp     short loc_180005491
0x180005423  lea     rcx, [rbx-18h]; this
0x180005427  cmp     [rax+1Ch], edx
0x18000542a  jnz     short loc_180005482
0x18000542c  test    byte ptr [rcx+38h], 10h
0x180005430  jz      short loc_18000543F
0x180005432  mov     ecx, cs:?s_acmiExtensionRootFolder@@3PAUtagCMENUITEM@@A; tagCMENUITEM near * s_acmiExtensionRootFolder
0x180005438  mov     eax, 1
0x18000543d  jmp     short loc_180005447
0x18000543f  mov     ecx, cs:?s_acmiRootFolder@@3PAUtagCMENUITEM@@A; tagCMENUITEM near * s_acmiRootFolder
0x180005445  xor     eax, eax
0x180005447  test    ecx, ecx
0x180005449  jz      short loc_18000549E
0x18000544b  mov     edi, [rdi]
0x18000544d  lea     rcx, ?s_acmiRootFolder@@3PAUtagCMENUITEM@@A; tagCMENUITEM near * s_acmiRootFolder
0x180005454  test    eax, eax
0x180005456  lea     rbx, ?s_acmiExtensionRootFolder@@3PAUtagCMENUITEM@@A; tagCMENUITEM near * s_acmiExtensionRootFolder
0x18000545d  cmovz   rbx, rcx
0x180005461  test    edx, edx
0x180005463  js      short loc_18000549E
0x180005465  test    [rbx+0Ch], edi
0x180005468  jz      short loc_180005477
0x18000546a  mov     rdx, rbx; struct tagCMENUITEM *
0x18000546d  mov     rcx, rsi; struct IContextMenuCallback *
0x180005470  call    ?AddCMenuItem@@YAJPEAUIContextMenuCallback@@PEAUtagCMENUITEM@@@Z; AddCMenuItem(IContextMenuCallback *,tagCMENUITEM *)
0x180005475  mov     edx, eax
0x180005477  add     rbx, 1Ch
0x18000547b  cmp     dword ptr [rbx], 0
0x18000547e  jnz     short loc_180005461
0x180005480  jmp     short loc_18000549E
0x180005482  mov     rdx, [rax+10h]; struct CLogInfo *
0x180005486  call    ?_UpdateCMenuItems@CComponentData@@AEAAXPEAVCLogInfo@@@Z; CComponentData::_UpdateCMenuItems(CLogInfo *)
0x18000548b  mov     r9d, 8000h; enum _DATA_OBJECT_TYPES
0x180005491  mov     r8d, [rdi]; unsigned int
0x180005494  mov     rdx, rsi; struct IContextMenuCallback *
0x180005497  call    ?_AddChildFolderContextMenuItems@CComponentData@@AEAAJPEAUIContextMenuCallback@@KW4_DATA_OBJECT_TYPES@@@Z; CComponentData::_AddChildFolderContextMenuItems(IContextMenuCallback *,ulong,_DATA_OBJECT_TYPES)
0x18000549c  mov     edx, eax
0x18000549e  mov     eax, edx
0x1800054a0  mov     rbx, [rsp+28h+arg_0]
0x1800054a5  mov     rsi, [rsp+28h+arg_8]
0x1800054aa  add     rsp, 20h
0x1800054ae  pop     rdi
0x1800054af  retn
```
