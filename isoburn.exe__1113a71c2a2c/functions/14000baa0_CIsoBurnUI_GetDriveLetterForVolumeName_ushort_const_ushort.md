# CIsoBurnUI::_GetDriveLetterForVolumeName(ushort const *,ushort *)

- ea: `0x14000baa0`
- end: `0x14000bbaa`
- name: `?_GetDriveLetterForVolumeName@CIsoBurnUI@@CAJPEBGPEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b3c0`
- `0x14000bd48`
- `0x14000be50`

## callees

- `0x14000baa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000bada`
- `KERNEL32!GetLastError` at `0x14000bada`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14000bacc`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14000bb21`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14000bacc`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x14000bb21`
- `api-ms-win-crt-private-l1-1-0!_o_isalpha` at `0x14000bb49`
- `api-ms-win-crt-private-l1-1-0!_o_isalpha` at `0x14000bb49`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x14000bb80`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x14000bb80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000bafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000bafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bb8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bb8f`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::_GetDriveLetterForVolumeName(LPCWSTR lpszVolumeName, unsigned __int16 *a2)
{
  unsigned int v4; // esi
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  WCHAR *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  DWORD cchBufferLength; // [rsp+50h] [rbp+18h] BYREF

  cchBufferLength = 0;
  v4 = -2147467259;
  if ( !GetVolumePathNamesForVolumeNameW(lpszVolumeName, 0, 0, &cchBufferLength) && GetLastError() == 234 )
  {
    if ( cchBufferLength )
    {
      v5 = (WCHAR *)CoTaskMemAlloc(2LL * cchBufferLength);
      v6 = v5;
      if ( v5 )
      {
        *v5 = 0;
        if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v5, cchBufferLength, &cchBufferLength) )
        {
          v7 = v6;
          if ( *v6 )
          {
            while ( 1 )
            {
              v8 = -1;
              do
                ++v8;
              while ( v7[v8] );
              if ( v8 == 3 && (unsigned int)_o_isalpha(*v7) && v7[1] == 58 && v7[2] == 92 )
                break;
              v9 = -1;
              do
                ++v9;
              while ( v7[v9] );
              v7 += v9 + 1;
              if ( !*v7 )
                goto LABEL_18;
            }
            *a2 = toupper(*v7);
            v4 = 0;
          }
        }
LABEL_18:
        CoTaskMemFree(v6);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14000baa0  mov     rax, rsp
0x14000baa3  mov     [rax+8], rbx
0x14000baa7  mov     [rax+10h], rbp
0x14000baab  push    rsi
0x14000baac  push    rdi
0x14000baad  push    r14
0x14000baaf  sub     rsp, 20h
0x14000bab3  mov     r14, rdx
0x14000bab6  lea     r9, [rax+18h]; lpcchReturnLength
0x14000baba  xor     ebp, ebp
0x14000babc  xor     edx, edx; lpszVolumePathNames
0x14000babe  xor     r8d, r8d; cchBufferLength
0x14000bac1  mov     [rax+18h], ebp
0x14000bac4  mov     rbx, rcx
0x14000bac7  mov     esi, 80004005h
0x14000bacc  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14000bad2  test    eax, eax
0x14000bad4  jnz     loc_14000BB95
0x14000bada  call    cs:__imp_GetLastError
0x14000bae0  cmp     eax, 0EAh
0x14000bae5  jnz     loc_14000BB95
0x14000baeb  mov     eax, [rsp+38h+cchBufferLength]
0x14000baef  test    eax, eax
0x14000baf1  jz      loc_14000BB95
0x14000baf7  mov     ecx, eax
0x14000baf9  add     rcx, rcx; cb
0x14000bafc  call    cs:__imp_CoTaskMemAlloc
0x14000bb02  mov     rdi, rax
0x14000bb05  test    rax, rax
0x14000bb08  jz      loc_14000BB95
0x14000bb0e  mov     [rax], bp
0x14000bb11  lea     r9, [rsp+38h+cchBufferLength]; lpcchReturnLength
0x14000bb16  mov     r8d, [rsp+38h+cchBufferLength]; cchBufferLength
0x14000bb1b  mov     rdx, rax; lpszVolumePathNames
0x14000bb1e  mov     rcx, rbx; lpszVolumeName
0x14000bb21  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x14000bb27  test    eax, eax
0x14000bb29  jz      short loc_14000BB8C
0x14000bb2b  mov     rbx, rdi
0x14000bb2e  cmp     [rdi], bp
0x14000bb31  jz      short loc_14000BB8C
0x14000bb33  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bb37  inc     rax
0x14000bb3a  cmp     [rbx+rax*2], bp
0x14000bb3e  jnz     short loc_14000BB37
0x14000bb40  cmp     rax, 3
0x14000bb44  jnz     short loc_14000BB61
0x14000bb46  movzx   ecx, word ptr [rbx]
0x14000bb49  call    cs:__imp__o_isalpha
0x14000bb4f  test    eax, eax
0x14000bb51  jz      short loc_14000BB61
0x14000bb53  cmp     word ptr [rbx+2], 3Ah ; ':'
0x14000bb58  jnz     short loc_14000BB61
0x14000bb5a  cmp     word ptr [rbx+4], 5Ch ; '\'
0x14000bb5f  jz      short loc_14000BB7D
0x14000bb61  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bb65  inc     rax
0x14000bb68  cmp     [rbx+rax*2], bp
0x14000bb6c  jnz     short loc_14000BB65
0x14000bb6e  lea     rbx, [rbx+rax*2]
0x14000bb72  add     rbx, 2
0x14000bb76  cmp     [rbx], bp
0x14000bb79  jnz     short loc_14000BB33
0x14000bb7b  jmp     short loc_14000BB8C
0x14000bb7d  movzx   ecx, word ptr [rbx]; C
0x14000bb80  call    cs:__imp_toupper
0x14000bb86  mov     [r14], ax
0x14000bb8a  mov     esi, ebp
0x14000bb8c  mov     rcx, rdi; pv
0x14000bb8f  call    cs:__imp_CoTaskMemFree
0x14000bb95  mov     rbx, [rsp+38h+arg_0]
0x14000bb9a  mov     eax, esi
0x14000bb9c  mov     rbp, [rsp+38h+arg_8]
0x14000bba1  add     rsp, 20h
0x14000bba5  pop     r14
0x14000bba7  pop     rdi
0x14000bba8  pop     rsi
0x14000bba9  retn
```
