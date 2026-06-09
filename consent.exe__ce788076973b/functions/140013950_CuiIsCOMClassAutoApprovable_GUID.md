# CuiIsCOMClassAutoApprovable(_GUID *)

- ea: `0x140013950`
- end: `0x140013a26`
- name: `?CuiIsCOMClassAutoApprovable@@YAHPEAU_GUID@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003820`

## callees

- `0x140013950`
- `0x140013a8c`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001398d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001398d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400139c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400139c3`

## string_xrefs

- `0x1400139b7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\UAC\COMAutoApprovalList`

## pseudocode

```c
__int64 __fastcall CuiIsCOMClassAutoApprovable(struct _GUID *a1)
{
  unsigned int v1; // ebx
  int pvData; // [rsp+40h] [rbp-78h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-74h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-68h] BYREF

  pvData = 0;
  v1 = 0;
  pcbData[0] = 4;
  sz[0] = 0;
  StringFromGUID2(a1, sz, 39);
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\UAC\\COMAutoApprovalList",
          sz,
          0x10u,
          0,
          &pvData,
          pcbData) )
    LOBYTE(v1) = pvData != 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      (unsigned int)WPP_3d93b7323a903a71f6d346154c1b1bb3_Traceguids,
      (unsigned int)sz,
      v1);
  return v1;
}

```

## disassembly

```asm
0x140013950  push    rbx
0x140013952  sub     rsp, 0B0h
0x140013959  mov     rax, cs:__security_cookie
0x140013960  xor     rax, rsp
0x140013963  mov     [rsp+0B8h+var_18], rax
0x14001396b  xor     eax, eax
0x14001396d  mov     [rsp+0B8h+var_78], 0
0x140013975  xor     ebx, ebx
0x140013977  mov     [rsp+0B8h+var_74], 4
0x14001397f  lea     rdx, [rsp+0B8h+sz]; lpsz
0x140013984  mov     [rsp+0B8h+sz], ax
0x140013989  lea     r8d, [rbx+27h]; cchMax
0x14001398d  call    cs:__imp_StringFromGUID2
0x140013993  lea     rax, [rsp+0B8h+var_74]
0x140013998  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001399f  mov     [rsp+0B8h+pcbData], rax; pcbData
0x1400139a4  lea     r9d, [rbx+10h]; dwFlags
0x1400139a8  lea     rax, [rsp+0B8h+var_78]
0x1400139ad  mov     [rsp+0B8h+pvData], rax; pvData
0x1400139b2  lea     r8, [rsp+0B8h+sz]; lpValue
0x1400139b7  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400139be  mov     [rsp+0B8h+pdwType], rbx; pdwType
0x1400139c3  call    cs:__imp_RegGetValueW
0x1400139c9  test    eax, eax
0x1400139cb  jnz     short loc_1400139D4
0x1400139cd  cmp     [rsp+0B8h+var_78], ebx
0x1400139d1  setnz   bl
0x1400139d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400139db  lea     rax, WPP_GLOBAL_Control
0x1400139e2  cmp     rcx, rax
0x1400139e5  jz      short loc_140013A0B
0x1400139e7  test    byte ptr [rcx+1Ch], 2
0x1400139eb  jz      short loc_140013A0B
0x1400139ed  mov     rcx, [rcx+10h]
0x1400139f1  lea     r9, [rsp+0B8h+sz]
0x1400139f6  mov     edx, 0Ah
0x1400139fb  mov     dword ptr [rsp+0B8h+pdwType], ebx
0x1400139ff  lea     r8, WPP_3d93b7323a903a71f6d346154c1b1bb3_Traceguids
0x140013a06  call    WPP_SF_Sd
0x140013a0b  mov     eax, ebx
0x140013a0d  mov     rcx, [rsp+0B8h+var_18]
0x140013a15  xor     rcx, rsp; StackCookie
0x140013a18  call    __security_check_cookie
0x140013a1d  add     rsp, 0B0h
0x140013a24  pop     rbx
0x140013a25  retn
```
