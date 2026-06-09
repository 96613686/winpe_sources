# NgscbLoadRegistryNameValuePairs(ushort const * *,ulong,_NGSCB_NAME_VALUE_COLLECTION * *)

- ea: `0x18002dbf0`
- end: `0x18002e68b`
- name: `?NgscbLoadRegistryNameValuePairs@@YAJPEAPEBGKPEAPEAU_NGSCB_NAME_VALUE_COLLECTION@@@Z`
- size: `2715`
- prototype: `__int64 __fastcall(const unsigned __int16 **, unsigned int, struct _NGSCB_NAME_VALUE_COLLECTION **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002c9c4`

## callees

- `0x1800090c0`
- `0x18002dbf0`
- `0x18002eed0`
- `0x18011efce`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e0a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e0a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dd45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e08d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dd45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e08d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dd59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dd59`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002e141`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002e141`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002de8c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002df5d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002de8c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002df5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dcea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e17a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dcea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e17a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ddd7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dc9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ddd7`

## pseudocode

```c
__int64 __fastcall NgscbLoadRegistryNameValuePairs(
        const unsigned __int16 **a1,
        __int64 a2,
        struct _NGSCB_NAME_VALUE_COLLECTION **a3)
{
  const unsigned __int16 **v3; // r15
  PVOID *v4; // rcx
  unsigned int v5; // esi
  DWORD v6; // r14d
  unsigned int v7; // edi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // r13d
  HANDLE ProcessHeap; // rax
  unsigned int *v13; // rax
  unsigned int *v14; // r12
  unsigned int v15; // r14d
  unsigned int v16; // edi
  HKEY v17; // rax
  LSTATUS v18; // eax
  PVOID *v19; // r10
  DWORD i; // r15d
  unsigned int v21; // edi
  char *v22; // rsi
  LSTATUS v23; // eax
  DWORD v24; // ecx
  unsigned __int64 v25; // rax
  unsigned int v26; // ecx
  BYTE *lpData; // r8
  unsigned int v28; // edx
  unsigned int v29; // edi
  LSTATUS v30; // eax
  unsigned int v31; // eax
  void **v32; // rax
  PVOID v33; // rcx
  __int64 v34; // rdx
  _QWORD *v35; // rcx
  HANDLE v36; // rax
  LSTATUS v37; // eax
  unsigned __int64 v38; // rax
  unsigned int v39; // edx
  DWORD v40; // r8d
  unsigned int v41; // eax
  __int64 v42; // rdx
  unsigned __int64 v43; // rdx
  __int64 v44; // rdx
  unsigned int v45; // [rsp+60h] [rbp-9h]
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-5h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-1h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD cValues; // [rsp+70h] [rbp+7h] BYREF
  DWORD v50; // [rsp+74h] [rbp+Bh]
  HKEY hKey[9]; // [rsp+78h] [rbp+Fh] BYREF
  DWORD cchValueName; // [rsp+D8h] [rbp+6Fh] BYREF
  struct _NGSCB_NAME_VALUE_COLLECTION **v54; // [rsp+E0h] [rbp+77h]
  DWORD cbMaxValueNameLen; // [rsp+E8h] [rbp+7Fh] BYREF

  v54 = a3;
  v3 = a1;
  hKey[0] = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cchValueName = 0;
  cbData = 0;
  Type = 0;
  if ( a3 )
  {
    if ( a1 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      v5 = 0;
      v50 = 0;
      v6 = 0;
      v7 = 0;
      while ( v7 < 2 )
      {
        if ( hKey[0] )
        {
          RegCloseKey(hKey[0]);
          hKey[0] = 0;
        }
        v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3[v7], 0, 0x20019u, hKey);
        v9 = v8;
        if ( v8 > 0 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        if ( v9 == -2147024894 )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          ++v7;
        }
        else
        {
          if ( v9 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
            if ( (v9 & 0x80000000) != 0 )
              goto LABEL_13;
          }
          v37 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
          v9 = v37;
          if ( v37 > 0 )
            v9 = (unsigned __int16)v37 | 0x80070000;
          if ( v9 )
          {
            v4 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
              v4 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (v9 & 0x80000000) != 0 )
              goto LABEL_13;
          }
          else
          {
            v4 = (PVOID *)WPP_GLOBAL_Control;
          }
          v38 = 2LL * cbMaxValueNameLen;
          if ( v38 > 0xFFFFFFFF )
          {
            cbMaxValueNameLen = -1;
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 201;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          v39 = v38 + 2;
          if ( (int)v38 + 2 < (unsigned int)v38 )
          {
            cbMaxValueNameLen = -1;
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 202;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          cbMaxValueNameLen = v38 + 2;
          v40 = cbMaxValueLen + 2;
          if ( cbMaxValueLen + 2 < cbMaxValueLen )
          {
            cbMaxValueLen = -1;
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 203;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          v41 = v39 + v40;
          cbMaxValueLen += 2;
          if ( v39 + v40 < v39 )
          {
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 204;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          v42 = v41 + 40;
          if ( (unsigned int)v42 < v41 )
          {
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 205;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          v43 = cValues * v42;
          if ( v43 > 0xFFFFFFFF )
          {
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 206;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          if ( (unsigned int)v43 + v5 < v5 )
          {
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 207;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          if ( v6 + cValues < v6 )
          {
            v9 = -2147024362;
            if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
            {
              v44 = 208;
              goto LABEL_170;
            }
            goto LABEL_13;
          }
          v5 += v43;
          v50 = v6 + cValues;
          v6 += cValues;
          ++v7;
        }
      }
      v11 = v5 + 24;
      if ( v5 + 24 < v5 )
      {
        v9 = -2147024362;
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v44 = 209;
          goto LABEL_170;
        }
      }
      else
      {
        if ( v11 < 0x18uLL )
        {
          v9 = -2147024809;
        }
        else
        {
          ProcessHeap = GetProcessHeap();
          v13 = (unsigned int *)HeapAlloc(ProcessHeap, 0, v11);
          v14 = v13;
          if ( v13 )
          {
            memset_0(v13, 0, v11);
            *v14 = v11;
            v15 = 24;
            v14[1] = 0;
            v16 = 0;
            *((_QWORD *)v14 + 2) = v14 + 2;
            *((_QWORD *)v14 + 1) = v14 + 2;
            v17 = hKey[0];
            while ( 1 )
            {
              v45 = v16;
              if ( v16 >= 2 )
              {
                v9 = NgscbDuplicateNameValuePairs((struct _NGSCB_NAME_VALUE_COLLECTION *)v14, 0, 0, v54, 0);
                if ( v9 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  {
                    v34 = 224;
LABEL_71:
                    v33 = (PVOID)v35[2];
LABEL_72:
                    WPP_SF_d(v33, v34, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
                  }
                }
                goto LABEL_66;
              }
              if ( v17 )
              {
                RegCloseKey(v17);
                hKey[0] = 0;
              }
              v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3[v16], 0, 0x20019u, hKey);
              v9 = v18;
              if ( v18 > 0 )
                v9 = (unsigned __int16)v18 | 0x80070000;
              if ( v9 != -2147024894 )
                break;
LABEL_62:
              v17 = hKey[0];
LABEL_63:
              v3 = a1;
              ++v16;
            }
            if ( v9 )
            {
              v19 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( (v9 & 0x80000000) != 0 )
                goto LABEL_66;
            }
            else
            {
              v19 = (PVOID *)WPP_GLOBAL_Control;
            }
            for ( i = 0; ; ++i )
            {
              v17 = hKey[0];
              if ( !hKey[0] || v14[1] >= v50 )
              {
                v16 = v45;
                goto LABEL_63;
              }
              v21 = v15 + 40;
              if ( v15 + 40 < v15 )
              {
                v9 = -2147024362;
                if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
                {
                  v33 = v19[2];
                  v34 = 212;
                  goto LABEL_72;
                }
                goto LABEL_66;
              }
              if ( v21 >= v11 )
                break;
              v22 = (char *)v14 + v15;
              *((_QWORD *)v22 + 2) = (char *)v14 + v21;
              cchValueName = (v11 - v21) >> 1;
              cbData = 0;
              v23 = RegEnumValueW(hKey[0], i, *((LPWSTR *)v22 + 2), &cchValueName, 0, &Type, 0, &cbData);
              v9 = v23;
              if ( v23 > 0 )
                v9 = (unsigned __int16)v23 | 0x80070000;
              if ( v9 == -2147024637 )
              {
LABEL_61:
                v16 = v45;
                goto LABEL_62;
              }
              if ( v9 )
              {
                v19 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    214,
                    &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                    v9);
                  v19 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( (v9 & 0x80000000) != 0 )
                  goto LABEL_66;
              }
              else
              {
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( Type == 1 )
              {
                v24 = cchValueName + 1;
                if ( cchValueName + 1 < cchValueName )
                {
                  cchValueName = -1;
                  v9 = -2147024362;
                  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
                  {
                    v33 = v19[2];
                    v34 = 215;
                    goto LABEL_72;
                  }
                  goto LABEL_66;
                }
                ++cchValueName;
                v25 = 2LL * v24;
                if ( v25 > 0xFFFFFFFF )
                {
                  v9 = -2147024362;
                  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
                  {
                    v33 = v19[2];
                    v34 = 216;
                    goto LABEL_72;
                  }
                  goto LABEL_66;
                }
                v26 = v25 + v21;
                if ( (unsigned int)v25 + v21 < v21 )
                {
                  v9 = -2147024362;
                  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
                  {
                    v33 = v19[2];
                    v34 = 217;
                    goto LABEL_72;
                  }
                  goto LABEL_66;
                }
                if ( v26 >= v11 )
                {
                  v9 = -2147418113;
                  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
                  {
                    v33 = v19[2];
                    v34 = 218;
                    goto LABEL_72;
                  }
                  goto LABEL_66;
                }
                lpData = (BYTE *)v14 + v26;
                *((_QWORD *)v22 + 3) = lpData;
                v28 = v26 + cbData;
                if ( v26 + cbData < v26 )
                {
                  v35 = WPP_GLOBAL_Control;
                  v9 = -2147024362;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  {
                    v34 = 219;
                    goto LABEL_71;
                  }
                  goto LABEL_66;
                }
                v29 = v28 + 2;
                if ( v28 + 2 < v28 )
                {
                  v35 = WPP_GLOBAL_Control;
                  v9 = -2147024362;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  {
                    v34 = 220;
                    goto LABEL_71;
                  }
                  goto LABEL_66;
                }
                if ( v29 >= v11 )
                {
                  v9 = -2147418113;
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  {
                    v34 = 221;
                    goto LABEL_71;
                  }
                  goto LABEL_66;
                }
                v30 = RegEnumValueW(hKey[0], i, *((LPWSTR *)v22 + 2), &cchValueName, 0, &Type, lpData, &cbData);
                v9 = v30;
                if ( v30 > 0 )
                  v9 = (unsigned __int16)v30 | 0x80070000;
                if ( v9 == -2147024637 )
                  goto LABEL_61;
                if ( v9 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      222,
                      &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
                      v9);
                  if ( (v9 & 0x80000000) != 0 )
                    goto LABEL_66;
                }
                v31 = v14[1];
                if ( v31 + 1 < v31 )
                {
                  v14[1] = -1;
                  v35 = WPP_GLOBAL_Control;
                  v9 = -2147024362;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                  {
                    v34 = 223;
                    goto LABEL_71;
                  }
                  goto LABEL_66;
                }
                v14[1] = v31 + 1;
                v32 = (void **)*((_QWORD *)v14 + 2);
                if ( *v32 != v14 + 2 )
                  __fastfail(3u);
                *(_QWORD *)v22 = v14 + 2;
                v15 = v29;
                *((_QWORD *)v22 + 1) = v32;
                *v32 = v22;
                *((_QWORD *)v14 + 2) = v22;
                v19 = (PVOID *)WPP_GLOBAL_Control;
              }
            }
            v9 = -2147418113;
            if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x40) != 0 )
            {
              v33 = v19[2];
              v34 = 213;
              goto LABEL_72;
            }
LABEL_66:
            v36 = GetProcessHeap();
            HeapFree(v36, 0, v14);
            goto LABEL_13;
          }
          v4 = (PVOID *)WPP_GLOBAL_Control;
          v9 = -2147024882;
        }
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v44 = 210;
          goto LABEL_170;
        }
      }
      goto LABEL_13;
    }
    v9 = -2147024809;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v9;
    v44 = 198;
  }
  else
  {
    v9 = -2147467261;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      return v9;
    v44 = 197;
  }
LABEL_170:
  WPP_SF_d(v4[2], v44, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
LABEL_13:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v9;
}

```

## disassembly

```asm
0x18002dbf0  mov     [rsp-8+arg_10], r8
0x18002dbf5  mov     [rsp-8+cchValueName], edx
0x18002dbf9  mov     [rsp-8+arg_0], rcx
0x18002dbfe  push    rbp
0x18002dbff  push    rbx
0x18002dc00  push    rsi
0x18002dc01  push    rdi
0x18002dc02  push    r12
0x18002dc04  push    r13
0x18002dc06  push    r14
0x18002dc08  push    r15
0x18002dc0a  lea     rbp, [rsp-1Fh]
0x18002dc0f  sub     rsp, 88h
0x18002dc16  xor     r13d, r13d
0x18002dc19  mov     r15, rcx
0x18002dc1c  mov     [rbp+57h+hKey], r13
0x18002dc20  mov     [rbp+57h+cValues], r13d
0x18002dc24  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18002dc28  mov     [rbp+57h+cbMaxValueLen], r13d
0x18002dc2c  mov     [rbp+57h+cchValueName], r13d
0x18002dc30  mov     [rbp+57h+cbData], r13d
0x18002dc34  mov     [rbp+57h+Type], r13d
0x18002dc38  test    r8, r8
0x18002dc3b  jz      loc_18002DCF8
0x18002dc41  test    rcx, rcx
0x18002dc44  jz      loc_18002E276
0x18002dc4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc51  lea     r12, WPP_GLOBAL_Control
0x18002dc58  mov     esi, r13d
0x18002dc5b  mov     [rbp+57h+var_4C], r13d
0x18002dc5f  mov     r14d, r13d
0x18002dc62  mov     edi, r13d
0x18002dc65  cmp     edi, 2
0x18002dc68  jnb     loc_18002DD2B
0x18002dc6e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002dc72  test    rcx, rcx
0x18002dc75  jnz     loc_18002E17A
0x18002dc7b  lea     rax, [rbp+57h+hKey]
0x18002dc7f  mov     edx, edi
0x18002dc81  mov     r9d, 20019h; samDesired
0x18002dc87  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002dc8c  xor     r8d, r8d; ulOptions
0x18002dc8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dc96  mov     rdx, [r15+rdx*8]; lpSubKey
0x18002dc9a  call    cs:__imp_RegOpenKeyExW
0x18002dca1  nop     dword ptr [rax+rax+00h]
0x18002dca6  mov     ebx, eax
0x18002dca8  test    eax, eax
0x18002dcaa  jle     short loc_18002DCB5
0x18002dcac  movzx   ebx, ax
0x18002dcaf  or      ebx, 80070000h
0x18002dcb5  cmp     ebx, 80070002h
0x18002dcbb  jz      loc_18002E047
0x18002dcc1  test    ebx, ebx
0x18002dcc3  jz      loc_18002E101
0x18002dcc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcd0  cmp     rcx, r12
0x18002dcd3  jnz     loc_18002E2A6
0x18002dcd9  test    ebx, ebx
0x18002dcdb  jns     loc_18002E101
0x18002dce1  mov     rcx, [rbp+57h+hKey]; hKey
0x18002dce5  test    rcx, rcx
0x18002dce8  jz      short loc_18002DD14
0x18002dcea  call    cs:__imp_RegCloseKey
0x18002dcf1  nop     dword ptr [rax+rax+00h]
0x18002dcf6  jmp     short loc_18002DD14
0x18002dcf8  mov     ebx, 80004003h
0x18002dcfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd04  lea     rax, WPP_GLOBAL_Control
0x18002dd0b  cmp     rcx, rax
0x18002dd0e  jnz     loc_18002E262
0x18002dd14  mov     eax, ebx
0x18002dd16  add     rsp, 88h
0x18002dd1d  pop     r15
0x18002dd1f  pop     r14
0x18002dd21  pop     r13
0x18002dd23  pop     r12
0x18002dd25  pop     rdi
0x18002dd26  pop     rsi
0x18002dd27  pop     rbx
0x18002dd28  pop     rbp
0x18002dd29  retn
0x18002dd2b  lea     r13d, [rsi+18h]
0x18002dd2f  cmp     r13d, esi
0x18002dd32  jb      loc_18002E656
0x18002dd38  mov     ebx, r13d
0x18002dd3b  cmp     rbx, 18h
0x18002dd3f  jb      loc_18002E3F5
0x18002dd45  call    cs:__imp_GetProcessHeap
0x18002dd4c  nop     dword ptr [rax+rax+00h]
0x18002dd51  mov     r8d, ebx; dwBytes
0x18002dd54  xor     edx, edx; dwFlags
0x18002dd56  mov     rcx, rax; hHeap
0x18002dd59  call    cs:__imp_HeapAlloc
0x18002dd60  nop     dword ptr [rax+rax+00h]
0x18002dd65  mov     r12, rax
0x18002dd68  test    rax, rax
0x18002dd6b  jz      loc_18002E3FF
0x18002dd71  mov     r8d, ebx; Size
0x18002dd74  xor     edx, edx; Val
0x18002dd76  mov     rcx, rax; void *
0x18002dd79  call    memset_0
0x18002dd7e  lea     rax, [r12+8]
0x18002dd83  mov     [r12], r13d
0x18002dd87  xor     r9d, r9d
0x18002dd8a  mov     r14d, 18h
0x18002dd90  mov     [r12+4], r9d
0x18002dd95  mov     edi, r9d
0x18002dd98  mov     [rax+8], rax
0x18002dd9c  mov     [rax], rax
0x18002dd9f  mov     rax, [rbp+57h+hKey]
0x18002dda3  mov     [rbp+57h+var_60], edi
0x18002dda6  cmp     edi, 2
0x18002dda9  jnb     loc_18002E0B2
0x18002ddaf  test    rax, rax
0x18002ddb2  jnz     loc_18002E055
0x18002ddb8  lea     rax, [rbp+57h+hKey]
0x18002ddbc  mov     edx, edi
0x18002ddbe  mov     r9d, 20019h; samDesired
0x18002ddc4  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18002ddc9  xor     r8d, r8d; ulOptions
0x18002ddcc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ddd3  mov     rdx, [r15+rdx*8]; lpSubKey
0x18002ddd7  call    cs:__imp_RegOpenKeyExW
0x18002ddde  nop     dword ptr [rax+rax+00h]
0x18002dde3  mov     ebx, eax
0x18002dde5  test    eax, eax
0x18002dde7  jle     short loc_18002DDF2
0x18002dde9  movzx   ebx, ax
0x18002ddec  or      ebx, 80070000h
0x18002ddf2  cmp     ebx, 80070002h
0x18002ddf8  jz      loc_18002E035
0x18002ddfe  xor     r9d, r9d
0x18002de01  test    ebx, ebx
0x18002de03  jnz     loc_18002E417
0x18002de09  mov     r10, cs:WPP_GLOBAL_Control
0x18002de10  mov     r15d, r9d
0x18002de13  mov     rax, [rbp+57h+hKey]
0x18002de17  test    rax, rax
0x18002de1a  jz      loc_18002E23D
0x18002de20  mov     ecx, [rbp+57h+var_4C]
0x18002de23  cmp     [r12+4], ecx
0x18002de28  jnb     loc_18002E23D
0x18002de2e  lea     edi, [r14+28h]
0x18002de32  cmp     edi, r14d
0x18002de35  jb      loc_18002DFD6
0x18002de3b  cmp     edi, r13d
0x18002de3e  jnb     loc_18002E628
0x18002de44  mov     esi, r14d
0x18002de47  mov     edx, r15d; dwIndex
0x18002de4a  add     rsi, r12
0x18002de4d  mov     eax, edi
0x18002de4f  add     rax, r12
0x18002de52  mov     [rsi+10h], rax
0x18002de56  mov     eax, r13d
0x18002de59  mov     rcx, [rbp+57h+hKey]; hKey
0x18002de5d  sub     eax, edi
0x18002de5f  shr     eax, 1
0x18002de61  mov     [rbp+57h+cchValueName], eax
0x18002de64  lea     rax, [rbp+57h+cbData]
0x18002de68  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18002de6d  lea     rax, [rbp+57h+Type]
0x18002de71  mov     [rsp+0C0h+lpData], r9; lpData
0x18002de76  mov     [rbp+57h+cbData], r9d
0x18002de7a  mov     r8, [rsi+10h]; lpValueName
0x18002de7e  mov     [rsp+0C0h+lpType], rax; lpType
0x18002de83  mov     [rsp+0C0h+phkResult], r9; lpReserved
0x18002de88  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002de8c  call    cs:__imp_RegEnumValueW
0x18002de93  nop     dword ptr [rax+rax+00h]
0x18002de98  mov     ebx, eax
0x18002de9a  test    eax, eax
0x18002de9c  jle     short loc_18002DEA7
0x18002de9e  movzx   ebx, ax
0x18002dea1  or      ebx, 80070000h
0x18002dea7  cmp     ebx, 80070103h
0x18002dead  jz      loc_18002E032
0x18002deb3  xor     r9d, r9d
0x18002deb6  test    ebx, ebx
0x18002deb8  jnz     loc_18002E460
0x18002debe  mov     r10, cs:WPP_GLOBAL_Control
0x18002dec5  cmp     [rbp+57h+Type], 1
0x18002dec9  jnz     loc_18002DFCE
0x18002decf  mov     eax, [rbp+57h+cchValueName]
0x18002ded2  lea     ecx, [rax+1]
0x18002ded5  cmp     ecx, eax
0x18002ded7  jb      loc_18002E004
0x18002dedd  mov     eax, ecx
0x18002dedf  mov     [rbp+57h+cchValueName], ecx
0x18002dee2  add     rax, rax
0x18002dee5  mov     ecx, 0FFFFFFFFh
0x18002deea  cmp     rax, rcx
0x18002deed  ja      loc_18002E5FA
0x18002def3  lea     ecx, [rax+rdi]
0x18002def6  cmp     ecx, edi
0x18002def8  jb      loc_18002E5CC
0x18002defe  cmp     ecx, r13d
0x18002df01  jnb     loc_18002E59E
0x18002df07  mov     r8d, ecx
0x18002df0a  add     r8, r12
0x18002df0d  mov     [rsi+18h], r8
0x18002df11  mov     edx, [rbp+57h+cbData]
0x18002df14  add     edx, ecx
0x18002df16  cmp     edx, ecx
0x18002df18  jb      loc_18002E56E
0x18002df1e  lea     edi, [rdx+2]
0x18002df21  cmp     edi, edx
0x18002df23  jb      loc_18002E53E
0x18002df29  cmp     edi, r13d
0x18002df2c  jnb     loc_18002E071
0x18002df32  mov     rcx, [rbp+57h+hKey]; hKey
0x18002df36  lea     rax, [rbp+57h+cbData]
0x18002df3a  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18002df3f  mov     edx, r15d; dwIndex
0x18002df42  mov     [rsp+0C0h+lpData], r8; lpData
0x18002df47  lea     rax, [rbp+57h+Type]
0x18002df4b  mov     r8, [rsi+10h]; lpValueName
0x18002df4f  mov     [rsp+0C0h+lpType], rax; lpType
0x18002df54  mov     [rsp+0C0h+phkResult], r9; lpReserved
0x18002df59  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18002df5d  call    cs:__imp_RegEnumValueW
0x18002df64  nop     dword ptr [rax+rax+00h]
0x18002df69  mov     ebx, eax
0x18002df6b  test    eax, eax
0x18002df6d  jle     short loc_18002DF78
0x18002df6f  movzx   ebx, ax
0x18002df72  or      ebx, 80070000h
0x18002df78  cmp     ebx, 80070103h
0x18002df7e  jz      loc_18002E032
0x18002df84  xor     r9d, r9d
0x18002df87  test    ebx, ebx
0x18002df89  jnz     loc_18002E4A9
0x18002df8f  mov     eax, [r12+4]
0x18002df94  lea     ecx, [rax+1]
0x18002df97  cmp     ecx, eax
0x18002df99  jb      loc_18002E4F1
0x18002df9f  mov     [r12+4], ecx
0x18002dfa4  lea     rcx, [r12+8]
0x18002dfa9  mov     rax, [rcx+8]
0x18002dfad  cmp     [rax], rcx
0x18002dfb0  jnz     loc_18002E4EA
0x18002dfb6  mov     [rsi], rcx
0x18002dfb9  mov     r14d, edi
0x18002dfbc  mov     [rsi+8], rax
0x18002dfc0  mov     [rax], rsi
0x18002dfc3  mov     [rcx+8], rsi
0x18002dfc7  mov     r10, cs:WPP_GLOBAL_Control
0x18002dfce  inc     r15d
0x18002dfd1  jmp     loc_18002DE13
0x18002dfd6  lea     rax, WPP_GLOBAL_Control
0x18002dfdd  mov     ebx, 80070216h
0x18002dfe2  cmp     r10, rax
0x18002dfe5  jz      loc_18002E08D
0x18002dfeb  test    byte ptr [r10+1Ch], 40h
0x18002dff0  jz      loc_18002E08D
0x18002dff6  mov     rcx, [r10+10h]
0x18002dffa  mov     edx, 0D4h
0x18002dfff  jmp     loc_18002E0F0
0x18002e004  mov     eax, 0FFFFFFFFh
0x18002e009  mov     [rbp+57h+cchValueName], eax
0x18002e00c  lea     rax, WPP_GLOBAL_Control
0x18002e013  mov     ebx, 80070216h
0x18002e018  cmp     r10, rax
0x18002e01b  jz      short loc_18002E08D
0x18002e01d  test    byte ptr [r10+1Ch], 40h
0x18002e022  jz      short loc_18002E08D
0x18002e024  mov     rcx, [r10+10h]
0x18002e028  mov     edx, 0D7h
0x18002e02d  jmp     loc_18002E0F0
0x18002e032  mov     edi, [rbp+57h+var_60]
0x18002e035  mov     rax, [rbp+57h+hKey]
0x18002e039  xor     r9d, r9d
0x18002e03c  mov     r15, [rbp+57h+arg_0]
0x18002e040  inc     edi
0x18002e042  jmp     loc_18002DDA3
0x18002e047  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e04e  inc     edi
0x18002e050  jmp     loc_18002DC65
0x18002e055  mov     rcx, rax; hKey
0x18002e058  call    cs:__imp_RegCloseKey
0x18002e05f  nop     dword ptr [rax+rax+00h]
0x18002e064  mov     [rbp+57h+hKey], 0
0x18002e06c  jmp     loc_18002DDB8
0x18002e071  mov     ebx, 8000FFFFh
0x18002e076  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e07d  lea     rax, WPP_GLOBAL_Control
0x18002e084  cmp     rcx, rax
0x18002e087  jnz     loc_18002E52A
0x18002e08d  call    cs:__imp_GetProcessHeap
0x18002e094  nop     dword ptr [rax+rax+00h]
0x18002e099  mov     r8, r12; lpMem
0x18002e09c  xor     edx, edx; dwFlags
0x18002e09e  mov     rcx, rax; hHeap
0x18002e0a1  call    cs:__imp_HeapFree
0x18002e0a8  nop     dword ptr [rax+rax+00h]
0x18002e0ad  jmp     loc_18002DCE1
0x18002e0b2  mov     [rsp+0C0h+phkResult], r9; struct _NGSCB_NAME_VALUE_ENTRY **
0x18002e0b7  xor     r8d, r8d; unsigned int
0x18002e0ba  mov     r9, [rbp+57h+arg_10]; struct _NGSCB_NAME_VALUE_COLLECTION **
0x18002e0be  xor     edx, edx; struct _NGSCB_NAME_VALUE_ENTRY *
  ... truncated ...
```
