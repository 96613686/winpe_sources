# DwAddLinkageKeysIfNotPresent(ushort *,ushort *,ushort *,ushort *,int *,ulong)

- ea: `0x18006cd08`
- end: `0x18006cf03`
- name: `?DwAddLinkageKeysIfNotPresent@@YAKPEAG000PEAHK@Z`
- size: `507`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18006c660`
- `0x18006c9b4`
- `0x18006d238`
- `0x18006d42c`

## callees

- `0x180028058`
- `0x18002812c`
- `0x18006cd08`
- `0x18006de6c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006ced6`
- `KERNEL32!LocalFree` at `0x18006ced6`
- `ADVAPI32!RegSetValueExW` at `0x18006ceab`
- `ADVAPI32!RegSetValueExW` at `0x18006ceab`
- `ADVAPI32!RegOpenKeyExW` at `0x18006cd62`
- `ADVAPI32!RegOpenKeyExW` at `0x18006cd62`
- `ADVAPI32!RegCloseKey` at `0x18006cec2`
- `ADVAPI32!RegCloseKey` at `0x18006cec2`

## pseudocode

```c
__int64 __fastcall DwAddLinkageKeysIfNotPresent(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int *a5,
        unsigned int a6)
{
  BYTE *lpData; // rbx
  unsigned int v9; // edi
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // r10d
  int v13; // r14d
  STRSAFE_LPWSTR v14; // rsi
  bool i; // zf
  __int64 v16; // r9
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  char *v19; // r8
  unsigned __int16 *v20; // rax
  signed __int64 v21; // r8
  int v22; // edx
  int v23; // ecx
  unsigned __int64 v24; // r11
  BYTE *v25; // rax
  _WORD *v26; // rcx
  unsigned int v28; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-10h] BYREF

  hKey = 0;
  v29 = 0;
  lpData = 0;
  *a5 = 0;
  pszDest = 0;
  v28 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hKey);
  if ( !v9 )
  {
    v11 = RegQueryValueWithAllocW(hKey, a3, v10, (unsigned __int8 **)&pszDest, &v28, &v29, a6);
    lpData = (BYTE *)pszDest;
    v9 = v11;
    if ( !v11 )
    {
      v12 = v28;
      v13 = 2;
      v14 = pszDest;
      for ( i = *pszDest == 0; !i; i = *v14 == 0 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v14[v16] );
        v17 = -1;
        do
          ++v17;
        while ( a4[v17] );
        if ( (unsigned int)v16 >= v17 )
        {
          v18 = -1;
          do
            ++v18;
          while ( a4[v18] );
          v19 = (char *)&v14[v18];
          if ( *(_WORD *)v19 == 123 )
          {
            v20 = a1;
            v21 = v19 - (char *)a1;
            do
            {
              v22 = *(unsigned __int16 *)((char *)v20 + v21);
              v23 = *v20 - v22;
              if ( v23 )
                break;
              ++v20;
            }
            while ( v22 );
            if ( !v23 )
            {
              *a5 = 1;
              break;
            }
          }
        }
        v14 += (unsigned int)v16 + 1;
        v12 += -2 - 2 * v16;
      }
      if ( !*a5 )
      {
        StringCchCopyW(v14, (unsigned __int64)v12 >> 1, a4);
        StringCchCatW(v14, v24, a1);
        v25 = lpData;
        while ( 1 )
        {
          i = *(_WORD *)v25 == 0;
          v26 = v25 + 2;
          v25 += 2;
          if ( i && !*v26 )
            break;
          ++v13;
        }
        v9 = RegSetValueExW(hKey, a3, 0, 7u, lpData, 2 * v13);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpData )
    LocalFree(lpData);
  return v9;
}

```

## disassembly

```asm
0x18006cd08  mov     r11, rsp
0x18006cd0b  mov     [r11+10h], rbx
0x18006cd0f  mov     [r11+18h], rsi
0x18006cd13  mov     [r11+20h], rdi
0x18006cd17  mov     [r11+8], rcx
0x18006cd1b  push    rbp
0x18006cd1c  push    r12
0x18006cd1e  push    r13
0x18006cd20  push    r14
0x18006cd22  push    r15
0x18006cd24  mov     rbp, rsp
0x18006cd27  sub     rsp, 60h
0x18006cd2b  mov     r15, [rbp+arg_20]
0x18006cd2f  lea     rax, [rbp+hKey]
0x18006cd33  xor     esi, esi
0x18006cd35  mov     [r11-68h], rax
0x18006cd39  mov     r12, r9
0x18006cd3c  mov     [rbp+hKey], rsi
0x18006cd40  mov     r13, r8
0x18006cd43  mov     [rbp+var_1C], esi
0x18006cd46  mov     ebx, esi
0x18006cd48  mov     [r15], esi
0x18006cd4b  mov     r9d, 0F003Fh; samDesired
0x18006cd51  mov     [rbp+pszDest], rbx
0x18006cd55  xor     r8d, r8d; ulOptions
0x18006cd58  mov     [rbp+var_20], esi
0x18006cd5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006cd62  call    cs:__imp_RegOpenKeyExW
0x18006cd69  nop     dword ptr [rax+rax+00h]
0x18006cd6e  mov     edi, eax
0x18006cd70  test    eax, eax
0x18006cd72  jnz     loc_18006CEB9
0x18006cd78  mov     eax, [rbp+arg_28]
0x18006cd7b  lea     r9, [rbp+pszDest]; unsigned __int8 **
0x18006cd7f  mov     rcx, [rbp+hKey]; hKey
0x18006cd83  mov     rdx, r13; lpValueName
0x18006cd86  mov     [rsp+60h+var_30], eax; unsigned int
0x18006cd8a  lea     rax, [rbp+var_1C]
0x18006cd8e  mov     qword ptr [rsp+60h+cbData], rax; unsigned int *
0x18006cd93  lea     rax, [rbp+var_20]
0x18006cd97  mov     [rsp+60h+lpData], rax; unsigned int *
0x18006cd9c  call    ?RegQueryValueWithAllocW@@YAKPEAUHKEY__@@PEAGKPEAPEAEPEAK3K@Z; RegQueryValueWithAllocW(HKEY__ *,ushort *,ulong,uchar * *,ulong *,ulong *,ulong)
0x18006cda1  mov     rbx, [rbp+pszDest]
0x18006cda5  mov     edi, eax
0x18006cda7  test    eax, eax
0x18006cda9  jnz     loc_18006CEB9
0x18006cdaf  mov     r10d, [rbp+var_20]
0x18006cdb3  lea     r14d, [rax+2]
0x18006cdb7  xor     edx, edx
0x18006cdb9  mov     rsi, rbx
0x18006cdbc  cmp     [rbx], dx
0x18006cdbf  jz      loc_18006CE4B
0x18006cdc5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006cdc9  mov     r9, rcx
0x18006cdcc  inc     r9
0x18006cdcf  cmp     [rsi+r9*2], dx
0x18006cdd4  jnz     short loc_18006CDCC
0x18006cdd6  mov     r11d, r9d
0x18006cdd9  mov     rax, rcx
0x18006cddc  inc     rax
0x18006cddf  cmp     [r12+rax*2], dx
0x18006cde4  jnz     short loc_18006CDDC
0x18006cde6  cmp     r11, rax
0x18006cde9  jb      short loc_18006CE27
0x18006cdeb  mov     rax, rcx
0x18006cdee  inc     rax
0x18006cdf1  cmp     [r12+rax*2], dx
0x18006cdf6  jnz     short loc_18006CDEE
0x18006cdf8  lea     r8, [rsi+rax*2]
0x18006cdfc  mov     eax, 7Bh ; '{'
0x18006ce01  cmp     ax, [r8]
0x18006ce05  jnz     short loc_18006CE27
0x18006ce07  mov     rax, [rbp+arg_0]
0x18006ce0b  sub     r8, rax
0x18006ce0e  movzx   ecx, word ptr [rax]
0x18006ce11  movzx   edx, word ptr [rax+r8]
0x18006ce16  sub     ecx, edx
0x18006ce18  jnz     short loc_18006CE21
0x18006ce1a  add     rax, r14
0x18006ce1d  test    edx, edx
0x18006ce1f  jnz     short loc_18006CE0E
0x18006ce21  xor     edx, edx
0x18006ce23  test    ecx, ecx
0x18006ce25  jz      short loc_18006CE44
0x18006ce27  lea     rsi, [rsi+r11*2]
0x18006ce2b  mov     ecx, 0FFFFFFFEh
0x18006ce30  lea     eax, [r9+r9]
0x18006ce34  add     rsi, r14
0x18006ce37  sub     ecx, eax
0x18006ce39  add     r10d, ecx
0x18006ce3c  cmp     [rsi], dx
0x18006ce3f  jmp     loc_18006CDBF
0x18006ce44  mov     dword ptr [r15], 1
0x18006ce4b  cmp     [r15], edx
0x18006ce4e  jnz     short loc_18006CEB9
0x18006ce50  mov     r11d, r10d
0x18006ce53  mov     r8, r12; pszSrc
0x18006ce56  shr     r11, 1
0x18006ce59  mov     rcx, rsi; pszDest
0x18006ce5c  mov     rdx, r11; cchDest
0x18006ce5f  call    StringCchCopyW
0x18006ce64  mov     r8, [rbp+arg_0]; unsigned __int16 *
0x18006ce68  mov     rdx, r11; unsigned __int64
0x18006ce6b  mov     rcx, rsi; unsigned __int16 *
0x18006ce6e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006ce73  mov     rax, rbx
0x18006ce76  xor     esi, esi
0x18006ce78  cmp     [rax], si
0x18006ce7b  lea     rcx, [rax+2]
0x18006ce7f  mov     rax, rcx
0x18006ce82  jnz     short loc_18006CE89
0x18006ce84  cmp     [rcx], si
0x18006ce87  jz      short loc_18006CE8E
0x18006ce89  inc     r14d
0x18006ce8c  jmp     short loc_18006CE78
0x18006ce8e  mov     rcx, [rbp+hKey]; hKey
0x18006ce92  lea     eax, [r14+r14]
0x18006ce96  mov     [rsp+60h+cbData], eax; cbData
0x18006ce9a  mov     r9d, 7; dwType
0x18006cea0  xor     r8d, r8d; Reserved
0x18006cea3  mov     [rsp+60h+lpData], rbx; lpData
0x18006cea8  mov     rdx, r13; lpValueName
0x18006ceab  call    cs:__imp_RegSetValueExW
0x18006ceb2  nop     dword ptr [rax+rax+00h]
0x18006ceb7  mov     edi, eax
0x18006ceb9  mov     rcx, [rbp+hKey]; hKey
0x18006cebd  test    rcx, rcx
0x18006cec0  jz      short loc_18006CECE
0x18006cec2  call    cs:__imp_RegCloseKey
0x18006cec9  nop     dword ptr [rax+rax+00h]
0x18006cece  test    rbx, rbx
0x18006ced1  jz      short loc_18006CEE2
0x18006ced3  mov     rcx, rbx; hMem
0x18006ced6  call    cs:__imp_LocalFree
0x18006cedd  nop     dword ptr [rax+rax+00h]
0x18006cee2  lea     r11, [rsp+60h+var_s0]
0x18006cee7  mov     eax, edi
0x18006cee9  mov     rbx, [r11+38h]
0x18006ceed  mov     rsi, [r11+40h]
0x18006cef1  mov     rdi, [r11+48h]
0x18006cef5  mov     rsp, r11
0x18006cef8  pop     r15
0x18006cefa  pop     r14
0x18006cefc  pop     r13
0x18006cefe  pop     r12
0x18006cf00  pop     rbp
0x18006cf01  retn
```
