# DeleteSystemRestorePoints(ushort const *)

- ea: `0x14000c678`
- end: `0x14000c900`
- name: `?DeleteSystemRestorePoints@@YAXPEBG@Z`
- size: `648`
- prototype: `void __fastcall(LPCWSTR lpszVolumeMountPoint)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000de50`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x1400094d4`
- `0x14000c678`
- `0x140018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000c819`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14000c819`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c8d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000c8d7`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14000c7ac`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14000c7c3`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14000c7ac`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x14000c7c3`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x14000c6c3`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x14000c6c3`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x14000c8a0`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x14000c8a0`

## pseudocode

```c
void __fastcall DeleteSystemRestorePoints(LPCWSTR lpszVolumeMountPoint)
{
  int v2; // esi
  int v3; // eax
  __int64 v4; // rbx
  GUID v5; // xmm6
  __int64 v6; // rdi
  GUID v7; // xmm1
  __int64 v8; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v10; // [rsp+58h] [rbp-B0h]
  __int64 v11; // [rsp+60h] [rbp-A8h]
  GUID v12; // [rsp+68h] [rbp-A0h] BYREF
  _OWORD v13[2]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v14[8]; // [rsp+98h] [rbp-70h] BYREF
  _OWORD v15[3]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-38h]
  __int64 v17; // [rsp+110h] [rbp+8h]
  WCHAR szVolumeName; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v19[526]; // [rsp+12Ah] [rbp+22h] BYREF
  WCHAR v20; // [rsp+338h] [rbp+230h] BYREF
  _BYTE v21[526]; // [rsp+33Ah] [rbp+232h] BYREF

  v9 = 0;
  v11 = 0;
  v2 = SHCoInitialize();
  if ( (int)CreateVssBackupComponentsInternal(&v9) >= 0 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, 0);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 280LL))(v9, 0xFFFFFFFFLL);
    v12 = GUID_NULL;
    v3 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v9 + 344LL))(v9, &v12, 1);
    if ( v3 >= 0 && v3 != 1 )
    {
      memset_0(v14, 0, 0x88u);
      v4 = 0;
      v5 = GUID_NULL;
      LODWORD(v8) = 1;
      szVolumeName = 0;
      memset_0(v19, 0, 0x206u);
      v20 = 0;
      memset_0(v21, 0, 0x206u);
      GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, &szVolumeName, 0x104u);
      GetVolumeNameForVolumeMountPointW(&szVolumeName, &v20, 0x104u);
      do
      {
        if ( (*(int (__fastcall **)(__int64, __int64, _BYTE *, __int64 *))(*(_QWORD *)v11 + 24LL))(v11, 1, v14, &v8) >= 0 )
        {
          if ( !(_DWORD)v8 )
            break;
          *(_QWORD *)&v12.Data1 = v15;
          if ( !(unsigned int)_o__wcsicmp(v16, &v20) )
          {
            if ( v4 )
            {
              v6 = v17;
              if ( v17 > v4 )
              {
                v7 = v5;
                v5 = (GUID)v15[0];
              }
              else
              {
                v7 = (GUID)v15[0];
              }
              LODWORD(v10) = 0;
              v13[1] = GUID_NULL;
              v13[0] = v7;
              (*(void (__fastcall **)(__int64, _OWORD *, __int64))(*(_QWORD *)v9 + 312LL))(v9, v13, 3);
              if ( v6 > v4 )
                v4 = v6;
            }
            else
            {
              v4 = v17;
              v5 = (GUID)v15[0];
            }
          }
          VssFreeSnapshotPropertiesInternal(v15);
        }
      }
      while ( (_DWORD)v8 );
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( !v2 )
    CoUninitialize();
}

```

## disassembly

```asm
0x14000c678  mov     rax, rsp
0x14000c67b  push    rbp
0x14000c67c  push    rbx
0x14000c67d  push    rsi
0x14000c67e  push    rdi
0x14000c67f  lea     rbp, [rax-488h]
0x14000c686  sub     rsp, 568h
0x14000c68d  movaps  xmmword ptr [rax-38h], xmm6
0x14000c691  mov     rax, cs:__security_cookie
0x14000c698  xor     rax, rsp
0x14000c69b  mov     [rbp+480h+var_40], rax
0x14000c6a2  mov     rdi, rcx
0x14000c6a5  mov     [rsp+580h+var_538], 0
0x14000c6ae  mov     qword ptr [rsp+580h+var_528], 0
0x14000c6b7  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x14000c6bc  mov     esi, eax
0x14000c6be  lea     rcx, [rsp+580h+var_538]
0x14000c6c3  call    cs:__imp_CreateVssBackupComponentsInternal
0x14000c6c9  test    eax, eax
0x14000c6cb  js      loc_14000C8D3
0x14000c6d1  mov     r8, [rsp+580h+var_538]
0x14000c6d6  mov     rcx, [r8]
0x14000c6d9  mov     rax, [rcx+28h]
0x14000c6dd  xor     edx, edx
0x14000c6df  mov     rcx, r8
0x14000c6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6e7  mov     rcx, [rsp+580h+var_538]
0x14000c6ec  mov     rax, [rcx]
0x14000c6ef  or      edx, 0FFFFFFFFh
0x14000c6f2  mov     rax, [rax+118h]
0x14000c6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6fe  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000c705  movdqu  [rsp+580h+var_528+8], xmm0
0x14000c70b  mov     rcx, [rsp+580h+var_538]
0x14000c710  mov     rax, [rcx]
0x14000c713  lea     rdx, [rsp+580h+var_528]
0x14000c718  mov     [rsp+580h+var_560], rdx
0x14000c71d  mov     r9d, 3
0x14000c723  lea     r8d, [r9-2]
0x14000c727  lea     rdx, [rsp+580h+var_528+8]
0x14000c72c  mov     rax, [rax+158h]
0x14000c733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c738  test    eax, eax
0x14000c73a  js      loc_14000C8C2
0x14000c740  cmp     eax, 1
0x14000c743  jz      loc_14000C8C2
0x14000c749  xor     edx, edx; Val
0x14000c74b  mov     r8d, 88h; Size
0x14000c751  lea     rcx, [rbp+480h+var_4F0]; void *
0x14000c755  call    memset_0
0x14000c75a  xor     ebx, ebx
0x14000c75c  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x14000c763  mov     dword ptr [rsp+580h+var_540], 1
0x14000c76b  xor     eax, eax
0x14000c76d  mov     [rbp+480h+szVolumeName], ax
0x14000c771  xor     edx, edx; Val
0x14000c773  mov     r8d, 206h; Size
0x14000c779  lea     rcx, [rbp+480h+var_45E]; void *
0x14000c77d  call    memset_0
0x14000c782  xor     eax, eax
0x14000c784  mov     [rbp+480h+var_250], ax
0x14000c78b  xor     edx, edx; Val
0x14000c78d  mov     r8d, 206h; Size
0x14000c793  lea     rcx, [rbp+480h+var_24E]; void *
0x14000c79a  call    memset_0
0x14000c79f  mov     r8d, 104h; cchBufferLength
0x14000c7a5  lea     rdx, [rbp+480h+szVolumeName]; lpszVolumeName
0x14000c7a9  mov     rcx, rdi; lpszVolumeMountPoint
0x14000c7ac  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14000c7b2  mov     r8d, 104h; cchBufferLength
0x14000c7b8  lea     rdx, [rbp+480h+var_250]; lpszVolumeName
0x14000c7bf  lea     rcx, [rbp+480h+szVolumeName]; lpszVolumeMountPoint
0x14000c7c3  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14000c7c9  cmp     dword ptr [rsp+580h+var_540], ebx
0x14000c7cd  jz      loc_14000C8B1
0x14000c7d3  mov     rcx, qword ptr [rsp+580h+var_528]
0x14000c7d8  mov     rax, [rcx]
0x14000c7db  lea     r9, [rsp+580h+var_540]
0x14000c7e0  lea     r8, [rbp+480h+var_4F0]
0x14000c7e4  mov     edx, 1
0x14000c7e9  mov     rax, [rax+18h]
0x14000c7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7f2  test    eax, eax
0x14000c7f4  js      loc_14000C8A6
0x14000c7fa  cmp     dword ptr [rsp+580h+var_540], 0
0x14000c7ff  jz      loc_14000C8B1
0x14000c805  lea     rax, [rbp+480h+var_4E8]
0x14000c809  mov     qword ptr [rsp+580h+var_528+8], rax
0x14000c80e  lea     rdx, [rbp+480h+var_250]
0x14000c815  mov     rcx, [rbp+480h+var_4B8]
0x14000c819  call    cs:__imp__o__wcsicmp
0x14000c81f  test    eax, eax
0x14000c821  jnz     short loc_14000C89C
0x14000c823  test    rbx, rbx
0x14000c826  jnz     short loc_14000C832
0x14000c828  mov     rbx, [rbp+480h+var_478]
0x14000c82c  movups  xmm6, [rbp+480h+var_4E8]
0x14000c830  jmp     short loc_14000C89C
0x14000c832  mov     rdi, [rbp+480h+var_478]
0x14000c836  cmp     rdi, rbx
0x14000c839  jg      short loc_14000C841
0x14000c83b  movups  xmm1, [rbp+480h+var_4E8]
0x14000c83f  jmp     short loc_14000C848
0x14000c841  movaps  xmm1, xmm6
0x14000c844  movups  xmm6, [rbp+480h+var_4E8]
0x14000c848  mov     dword ptr [rsp+580h+var_530], 0
0x14000c850  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000c857  movdqu  [rbp+480h+var_500], xmm0
0x14000c85c  movdqa  [rsp+580h+var_518+8], xmm1
0x14000c862  mov     rcx, [rsp+580h+var_538]
0x14000c867  mov     rax, [rcx]
0x14000c86a  lea     rdx, [rbp+480h+var_500]
0x14000c86e  mov     [rsp+28h], rdx
0x14000c873  lea     rdx, [rsp+580h+var_530]
0x14000c878  mov     [rsp+580h+var_560], rdx
0x14000c87d  xor     r9d, r9d
0x14000c880  lea     r8d, [r9+3]
0x14000c884  lea     rdx, [rsp+580h+var_518+8]
0x14000c889  mov     rax, [rax+138h]
0x14000c890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c895  cmp     rdi, rbx
0x14000c898  cmovg   rbx, rdi
0x14000c89c  lea     rcx, [rbp+480h+var_4E8]
0x14000c8a0  call    cs:__imp_VssFreeSnapshotPropertiesInternal
0x14000c8a6  cmp     dword ptr [rsp+580h+var_540], 0
0x14000c8ab  jnz     loc_14000C7D3
0x14000c8b1  mov     rcx, qword ptr [rsp+580h+var_528]
0x14000c8b6  mov     rax, [rcx]
0x14000c8b9  mov     rax, [rax+10h]
0x14000c8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8c2  mov     rcx, [rsp+580h+var_538]
0x14000c8c7  mov     rax, [rcx]
0x14000c8ca  mov     rax, [rax+10h]
0x14000c8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8d3  test    esi, esi
0x14000c8d5  jnz     short loc_14000C8DD
0x14000c8d7  call    cs:__imp_CoUninitialize
0x14000c8dd  mov     rcx, [rbp+480h+var_40]
0x14000c8e4  xor     rcx, rsp; StackCookie
0x14000c8e7  call    __security_check_cookie
0x14000c8ec  movaps  xmm6, [rsp+580h+var_38+8]
0x14000c8f4  add     rsp, 568h
0x14000c8fb  pop     rdi
0x14000c8fc  pop     rsi
0x14000c8fd  pop     rbx
0x14000c8fe  pop     rbp
0x14000c8ff  retn
```
