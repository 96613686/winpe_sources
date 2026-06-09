# DllGetClassObject

- ea: `0x180195930`
- end: `0x180195a92`
- name: `DllGetClassObject`
- size: `354`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180195930`
- `0x1801aacd0`
- `0x1801dd020`
- `0x1801dd670`
- `0x1801fddc8`
- `0x1801fde50`
- `0x1801fe2c4`
- `0x1801fe340`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18019598d`
- `RPCRT4!NdrDllGetClassObject` at `0x18019598d`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rcx
  HRESULT result; // eax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdi
  HRESULT v12; // ebx

  if ( &off_18036C710 )
    pclsid = (const CLSID *)&qword_1803B9830;
  else
    pclsid = 0;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&pProxyFileList, pclsid, &pPSFactoryBuffer);
  if ( result == -2147221231 )
  {
    v5 = *(_QWORD *)&rclsid->Data1 - 0x4C8BA30B16D51579LL;
    if ( *(_QWORD *)&rclsid->Data1 == 0x4C8BA30B16D51579LL )
      v5 = *(_QWORD *)rclsid->Data4 - 0x55E741DCF40F76A2LL;
    if ( v5 )
    {
      v7 = *(_QWORD *)&rclsid->Data1 - 0x42E686AB34A13FC7LL;
      if ( *(_QWORD *)&rclsid->Data1 == 0x42E686AB34A13FC7LL )
        v7 = *(_QWORD *)rclsid->Data4 + 0x6B00F99F94AD35DLL;
      if ( v7 )
      {
        v8 = *(_QWORD *)&rclsid->Data1 - 0x4A535EFB197060CBLL;
        if ( *(_QWORD *)&rclsid->Data1 == 0x4A535EFB197060CBLL )
          v8 = *(_QWORD *)rclsid->Data4 - 0x7C6231BB9D9342B0LL;
        if ( v8 )
        {
          v9 = *(_QWORD *)&rclsid->Data1 - 0x4ADCC7DFC7875EEFLL;
          if ( *(_QWORD *)&rclsid->Data1 == 0x4ADCC7DFC7875EEFLL )
            v9 = *(_QWORD *)rclsid->Data4 + 0x6EEBF33E90FA2661LL;
          if ( v9 )
          {
            v10 = *(_QWORD *)&rclsid->Data1 - 0x465C6E6A842A1268LL;
            if ( *(_QWORD *)&rclsid->Data1 == 0x465C6E6A842A1268LL )
              v10 = *(_QWORD *)rclsid->Data4 + 0x707D46BA3B74707ALL;
            if ( v10 )
              return -2147221231;
            v6 = sub_1801FE340();
          }
          else
          {
            v6 = sub_1801FDE50();
          }
        }
        else
        {
          v6 = sub_1801FE2C4();
        }
      }
      else
      {
        v6 = sub_1801FDDC8();
      }
    }
    else
    {
      v6 = sub_1801AACD0();
    }
    v11 = v6;
    if ( v6 )
    {
      v12 = sub_1801DD020(v6, riid, ppv);
      sub_1801DD670(v11);
      return v12;
    }
    else
    {
      *ppv = 0;
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180195930  mov     [rsp+ppv], r8
0x180195935  mov     [rsp+riid], rdx
0x18019593a  mov     [rsp+rclsid], rcx
0x18019593f  push    rbx
0x180195940  push    rsi
0x180195941  push    rdi
0x180195942  sub     rsp, 30h
0x180195946  mov     rax, cs:pProxyFileList
0x18019594d  mov     rcx, [rax+8]
0x180195951  mov     rax, [rcx]
0x180195954  test    rax, rax
0x180195957  jz      short loc_18019595E
0x180195959  mov     rcx, [rax]
0x18019595c  jmp     short loc_180195960
0x18019595e  xor     ecx, ecx
0x180195960  mov     rsi, [rsp+48h+ppv]
0x180195965  lea     rax, pPSFactoryBuffer
0x18019596c  mov     rbx, [rsp+48h+rclsid]
0x180195971  lea     r9, pProxyFileList; pProxyFileList
0x180195978  mov     rdx, [rsp+48h+riid]; riid
0x18019597d  mov     r8, rsi; ppv
0x180195980  mov     [rsp+48h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180195985  mov     [rsp+48h+pclsid], rcx; pclsid
0x18019598a  mov     rcx, rbx; rclsid
0x18019598d  call    cs:NdrDllGetClassObject
0x180195993  test    eax, eax
0x180195995  jz      loc_180195A8A
0x18019599b  mov     ecx, 80040111h
0x1801959a0  cmp     eax, ecx
0x1801959a2  jnz     loc_180195A8A
0x1801959a8  mov     rax, [rbx]
0x1801959ab  sub     rax, cs:qword_1803BB770
0x1801959b2  jnz     short loc_1801959BF
0x1801959b4  mov     rax, [rbx+8]
0x1801959b8  sub     rax, cs:qword_1803BB778
0x1801959bf  test    rax, rax
0x1801959c2  jnz     short loc_1801959CE
0x1801959c4  call    sub_1801AACD0
0x1801959c9  jmp     loc_180195A58
0x1801959ce  mov     rax, [rbx]
0x1801959d1  sub     rax, cs:qword_1803BB780
0x1801959d8  jnz     short loc_1801959E5
0x1801959da  mov     rax, [rbx+8]
0x1801959de  sub     rax, cs:qword_1803BB788
0x1801959e5  test    rax, rax
0x1801959e8  jnz     short loc_1801959F1
0x1801959ea  call    sub_1801FDDC8
0x1801959ef  jmp     short loc_180195A58
0x1801959f1  mov     rax, [rbx]
0x1801959f4  sub     rax, cs:qword_1803BB7A0
0x1801959fb  jnz     short loc_180195A08
0x1801959fd  mov     rax, [rbx+8]
0x180195a01  sub     rax, cs:qword_1803BB7A8
0x180195a08  test    rax, rax
0x180195a0b  jnz     short loc_180195A14
0x180195a0d  call    sub_1801FE2C4
0x180195a12  jmp     short loc_180195A58
0x180195a14  mov     rax, [rbx]
0x180195a17  sub     rax, cs:qword_1803BB760
0x180195a1e  jnz     short loc_180195A2B
0x180195a20  mov     rax, [rbx+8]
0x180195a24  sub     rax, cs:qword_1803BB768
0x180195a2b  test    rax, rax
0x180195a2e  jnz     short loc_180195A37
0x180195a30  call    sub_1801FDE50
0x180195a35  jmp     short loc_180195A58
0x180195a37  mov     rax, [rbx]
0x180195a3a  sub     rax, cs:qword_1803BB790
0x180195a41  jnz     short loc_180195A4E
0x180195a43  mov     rax, [rbx+8]
0x180195a47  sub     rax, cs:qword_1803BB798
0x180195a4e  test    rax, rax
0x180195a51  jnz     short loc_180195A88
0x180195a53  call    sub_1801FE340
0x180195a58  mov     rdi, rax
0x180195a5b  test    rax, rax
0x180195a5e  jnz     short loc_180195A6A
0x180195a60  mov     [rsi], rax
0x180195a63  mov     eax, 8007000Eh
0x180195a68  jmp     short loc_180195A8A
0x180195a6a  mov     rdx, [rsp+48h+riid]
0x180195a6f  mov     r8, rsi
0x180195a72  mov     rcx, rdi
0x180195a75  call    sub_1801DD020
0x180195a7a  mov     rcx, rdi
0x180195a7d  mov     ebx, eax
0x180195a7f  call    sub_1801DD670
0x180195a84  mov     eax, ebx
0x180195a86  jmp     short loc_180195A8A
0x180195a88  mov     eax, ecx
0x180195a8a  add     rsp, 30h
0x180195a8e  pop     rdi
0x180195a8f  pop     rsi
0x180195a90  pop     rbx
0x180195a91  retn
```
