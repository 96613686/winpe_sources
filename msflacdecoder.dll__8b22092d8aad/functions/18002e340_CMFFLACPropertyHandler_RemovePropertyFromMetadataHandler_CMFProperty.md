# CMFFLACPropertyHandler::RemovePropertyFromMetadataHandler(CMFProperty *)

- ea: `0x18002e340`
- end: `0x18002e40d`
- name: `?RemovePropertyFromMetadataHandler@CMFFLACPropertyHandler@@AEAAJPEAVCMFProperty@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CMFFLACPropertyHandler *__hidden this, struct CMFProperty *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e1e0`

## callees

- `0x180020484`
- `0x18002e340`
- `0x1800309d0`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e3fa`

## pseudocode

```c
__int64 __fastcall CMFFLACPropertyHandler::RemovePropertyFromMetadataHandler(
        CMFFLACPropertyHandler *this,
        struct CMFProperty *a2)
{
  __int64 v2; // rax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+48h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+50h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a2;
  pv = 0;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(struct CMFProperty *, __int64 *, LPVOID *, int *))(v2 + 104))(
         a2,
         MF_MD_NAME,
         &pv,
         &v8);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_11;
    v6 = 44;
    goto LABEL_10;
  }
  v4 = CFLACMetadataWriter::DeleteProperty((CMFFLACPropertyHandler *)((char *)this + 1984), (char *)pv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *((_DWORD *)this + 530) = 1;
    goto LABEL_11;
  }
  if ( v4 == -1072873843 )
  {
    v5 = 0;
    goto LABEL_11;
  }
  if ( g_wppLevels )
  {
    v6 = 45;
LABEL_10:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids, this, v4);
  }
LABEL_11:
  if ( pv )
    CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x18002e340  mov     r11, rsp
0x18002e343  mov     [r11+8], rbx
0x18002e347  push    rdi
0x18002e348  sub     rsp, 30h
0x18002e34c  mov     rax, [rdx]
0x18002e34f  lea     r9, [r11+10h]
0x18002e353  mov     r10, rdx
0x18002e356  mov     qword ptr [r11+18h], 0
0x18002e35e  mov     rdi, rcx
0x18002e361  mov     [rsp+38h+arg_8], 0
0x18002e369  lea     r8, [r11+18h]
0x18002e36d  mov     rcx, r10
0x18002e370  mov     rax, [rax+68h]
0x18002e374  lea     rdx, MF_MD_NAME
0x18002e37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e380  mov     ebx, eax
0x18002e382  test    eax, eax
0x18002e384  jns     short loc_18002E396
0x18002e386  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e38d  jb      short loc_18002E3F0
0x18002e38f  mov     edx, 2Ch ; ','
0x18002e394  jmp     short loc_18002E3D2
0x18002e396  mov     rdx, [rsp+38h+pv]; unsigned __int16 *
0x18002e39b  lea     rcx, [rdi+7C0h]; this
0x18002e3a2  call    ?DeleteProperty@CFLACMetadataWriter@@UEAAJPEBG@Z; CFLACMetadataWriter::DeleteProperty(ushort const *)
0x18002e3a7  mov     ebx, eax
0x18002e3a9  test    eax, eax
0x18002e3ab  js      short loc_18002E3B9
0x18002e3ad  mov     dword ptr [rdi+848h], 1
0x18002e3b7  jmp     short loc_18002E3F0
0x18002e3b9  cmp     eax, 0C00D3E8Dh
0x18002e3be  jnz     short loc_18002E3C4
0x18002e3c0  xor     ebx, ebx
0x18002e3c2  jmp     short loc_18002E3F0
0x18002e3c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002e3cb  jb      short loc_18002E3F0
0x18002e3cd  mov     edx, 2Dh ; '-'
0x18002e3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3d9  lea     r8, WPP_36e4e3a47ce73e52b63ec011625d5c06_Traceguids
0x18002e3e0  mov     r9, rdi
0x18002e3e3  mov     [rsp+38h+var_18], eax
0x18002e3e7  mov     rcx, [rcx+10h]
0x18002e3eb  call    WPP_SF_qd
0x18002e3f0  mov     rcx, [rsp+38h+pv]; pv
0x18002e3f5  test    rcx, rcx
0x18002e3f8  jz      short loc_18002E400
0x18002e3fa  call    cs:__imp_CoTaskMemFree
0x18002e400  mov     eax, ebx
0x18002e402  mov     rbx, [rsp+38h+arg_0]
0x18002e407  add     rsp, 30h
0x18002e40b  pop     rdi
0x18002e40c  retn
```
