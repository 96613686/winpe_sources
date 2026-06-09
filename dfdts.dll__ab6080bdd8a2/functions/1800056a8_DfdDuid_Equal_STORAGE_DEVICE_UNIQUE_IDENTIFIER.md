# DfdDuid::Equal(_STORAGE_DEVICE_UNIQUE_IDENTIFIER *)

- ea: `0x1800056a8`
- end: `0x1800058ed`
- name: `?Equal@DfdDuid@@QEAAHPEAU_STORAGE_DEVICE_UNIQUE_IDENTIFIER@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(DfdDuid *__hidden this, struct _STORAGE_DEVICE_UNIQUE_IDENTIFIER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800061f4`

## callees

- `0x180002c68`
- `0x18000536c`
- `0x1800056a8`

## pseudocode

```c
__int64 __fastcall DfdDuid::Equal(DfdDuid *this, struct _STORAGE_DEVICE_UNIQUE_IDENTIFIER *a2)
{
  __int64 v4; // rdx
  char v5; // si
  __int64 v6; // rcx
  __int64 v7; // rdx
  char v8; // di
  int v9; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  _QWORD *v18; // rcx
  __int64 v19; // rdx

  if ( a2
    && (v4 = *((unsigned int *)a2 + 3), (_DWORD)v4)
    && (unsigned int)(*((_DWORD *)a2 + 1) - v4) >= 0x28
    && *(_DWORD *)((char *)a2 + v4 + 4) >= 0x28u
    && *(_DWORD *)((char *)a2 + v4 + 24) == -1 )
  {
    *(_DWORD *)((char *)a2 + v4 + 24) = 0;
    v5 = 1;
  }
  else
  {
    v5 = 0;
  }
  v6 = *((_QWORD *)this + 2);
  if ( v6
    && (v7 = *(unsigned int *)(v6 + 12), (_DWORD)v7)
    && (unsigned int)(*(_DWORD *)(v6 + 4) - v7) >= 0x28
    && *(_DWORD *)(v7 + v6 + 4) >= 0x28u
    && *(_DWORD *)(v7 + v6 + 24) == -1 )
  {
    *(_DWORD *)(v7 + v6 + 24) = 0;
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  v9 = CompareStorageDuids((unsigned int *)a2, *((_DWORD **)this + 2));
  if ( v5 )
    *(_DWORD *)((char *)a2 + *((unsigned int *)a2 + 3) + 24) = -1;
  if ( v8 )
    *(_DWORD *)(*(unsigned int *)(*((_QWORD *)this + 2) + 12LL) + *((_QWORD *)this + 2) + 24LL) = -1;
  if ( !v9 )
    return 1;
  v11 = v9 - 100;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              v17 = v16 - 1;
              if ( v17 )
              {
                if ( v17 != 1 )
                  return 0;
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  return 0;
                }
                v19 = 23;
              }
              else
              {
                v18 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  return 0;
                }
                v19 = 22;
              }
            }
            else
            {
              v18 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                return 0;
              }
              v19 = 21;
            }
          }
          else
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return 0;
            v19 = 20;
          }
        }
        else
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return 0;
          v19 = 19;
        }
      }
      else
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return 0;
        v19 = 18;
      }
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v19 = 17;
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v19 = 16;
  }
  WPP_SF_(v18[2], v19, &WPP_3fe3f72127b734931da4de68e0accc84_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800056a8  push    rbx
0x1800056aa  push    rbp
0x1800056ab  push    rsi
0x1800056ac  push    rdi
0x1800056ad  sub     rsp, 28h
0x1800056b1  mov     rbx, rdx
0x1800056b4  mov     rbp, rcx
0x1800056b7  test    rdx, rdx
0x1800056ba  jz      short loc_1800056E8
0x1800056bc  mov     edx, [rdx+0Ch]
0x1800056bf  test    edx, edx
0x1800056c1  jz      short loc_1800056E8
0x1800056c3  mov     eax, [rbx+4]
0x1800056c6  sub     eax, edx
0x1800056c8  cmp     eax, 28h ; '('
0x1800056cb  jb      short loc_1800056E8
0x1800056cd  cmp     dword ptr [rdx+rbx+4], 28h ; '('
0x1800056d2  jb      short loc_1800056E8
0x1800056d4  cmp     dword ptr [rdx+rbx+18h], 0FFFFFFFFh
0x1800056d9  jnz     short loc_1800056E8
0x1800056db  mov     dword ptr [rdx+rbx+18h], 0
0x1800056e3  mov     sil, 1
0x1800056e6  jmp     short loc_1800056EB
0x1800056e8  xor     sil, sil
0x1800056eb  mov     rcx, [rcx+10h]
0x1800056ef  test    rcx, rcx
0x1800056f2  jz      short loc_180005720
0x1800056f4  mov     edx, [rcx+0Ch]
0x1800056f7  test    edx, edx
0x1800056f9  jz      short loc_180005720
0x1800056fb  mov     eax, [rcx+4]
0x1800056fe  sub     eax, edx
0x180005700  cmp     eax, 28h ; '('
0x180005703  jb      short loc_180005720
0x180005705  cmp     dword ptr [rdx+rcx+4], 28h ; '('
0x18000570a  jb      short loc_180005720
0x18000570c  cmp     dword ptr [rdx+rcx+18h], 0FFFFFFFFh
0x180005711  jnz     short loc_180005720
0x180005713  mov     dword ptr [rdx+rcx+18h], 0
0x18000571b  mov     dil, 1
0x18000571e  jmp     short loc_180005723
0x180005720  xor     dil, dil
0x180005723  mov     rdx, [rbp+10h]
0x180005727  mov     rcx, rbx
0x18000572a  call    ?CompareStorageDuids@@YA?AW4_DUID_MATCH_STATUS@@PEAU_STORAGE_DEVICE_UNIQUE_IDENTIFIER@@0@Z; CompareStorageDuids(_STORAGE_DEVICE_UNIQUE_IDENTIFIER *,_STORAGE_DEVICE_UNIQUE_IDENTIFIER *)
0x18000572f  mov     r8d, eax
0x180005732  test    sil, sil
0x180005735  jz      short loc_180005742
0x180005737  mov     ecx, [rbx+0Ch]
0x18000573a  mov     dword ptr [rcx+rbx+18h], 0FFFFFFFFh
0x180005742  test    dil, dil
0x180005745  jz      short loc_180005756
0x180005747  mov     rdx, [rbp+10h]
0x18000574b  mov     ecx, [rdx+0Ch]
0x18000574e  mov     dword ptr [rcx+rdx+18h], 0FFFFFFFFh
0x180005756  test    r8d, r8d
0x180005759  jnz     short loc_180005764
0x18000575b  lea     eax, [r8+1]
0x18000575f  jmp     loc_1800058E4
0x180005764  sub     r8d, 64h ; 'd'
0x180005768  jz      loc_1800058B4
0x18000576e  sub     r8d, 1
0x180005772  jz      loc_180005894
0x180005778  sub     r8d, 1
0x18000577c  jz      loc_180005874
0x180005782  sub     r8d, 1
0x180005786  jz      loc_180005854
0x18000578c  sub     r8d, 1
0x180005790  jz      loc_18000582C
0x180005796  sub     r8d, 1
0x18000579a  jz      short loc_180005801
0x18000579c  sub     r8d, 1
0x1800057a0  jz      short loc_1800057D6
0x1800057a2  cmp     r8d, 1
0x1800057a6  jnz     loc_1800058E2
0x1800057ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057b3  lea     rax, WPP_GLOBAL_Control
0x1800057ba  cmp     rcx, rax
0x1800057bd  jz      loc_1800058E2
0x1800057c3  test    [rcx+1Ch], r8b
0x1800057c7  jz      loc_1800058E2
0x1800057cd  lea     edx, [r8+16h]
0x1800057d1  jmp     loc_1800058D2
0x1800057d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057dd  lea     rax, WPP_GLOBAL_Control
0x1800057e4  cmp     rcx, rax
0x1800057e7  jz      loc_1800058E2
0x1800057ed  test    byte ptr [rcx+1Ch], 1
0x1800057f1  jz      loc_1800058E2
0x1800057f7  mov     edx, 16h
0x1800057fc  jmp     loc_1800058D2
0x180005801  mov     rcx, cs:WPP_GLOBAL_Control
0x180005808  lea     rax, WPP_GLOBAL_Control
0x18000580f  cmp     rcx, rax
0x180005812  jz      loc_1800058E2
0x180005818  test    byte ptr [rcx+1Ch], 1
0x18000581c  jz      loc_1800058E2
0x180005822  mov     edx, 15h
0x180005827  jmp     loc_1800058D2
0x18000582c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005833  lea     rax, WPP_GLOBAL_Control
0x18000583a  cmp     rcx, rax
0x18000583d  jz      loc_1800058E2
0x180005843  test    byte ptr [rcx+1Ch], 1
0x180005847  jz      loc_1800058E2
0x18000584d  mov     edx, 14h
0x180005852  jmp     short loc_1800058D2
0x180005854  mov     rcx, cs:WPP_GLOBAL_Control
0x18000585b  lea     rax, WPP_GLOBAL_Control
0x180005862  cmp     rcx, rax
0x180005865  jz      short loc_1800058E2
0x180005867  test    byte ptr [rcx+1Ch], 1
0x18000586b  jz      short loc_1800058E2
0x18000586d  mov     edx, 13h
0x180005872  jmp     short loc_1800058D2
0x180005874  mov     rcx, cs:WPP_GLOBAL_Control
0x18000587b  lea     rax, WPP_GLOBAL_Control
0x180005882  cmp     rcx, rax
0x180005885  jz      short loc_1800058E2
0x180005887  test    byte ptr [rcx+1Ch], 1
0x18000588b  jz      short loc_1800058E2
0x18000588d  mov     edx, 12h
0x180005892  jmp     short loc_1800058D2
0x180005894  mov     rcx, cs:WPP_GLOBAL_Control
0x18000589b  lea     rax, WPP_GLOBAL_Control
0x1800058a2  cmp     rcx, rax
0x1800058a5  jz      short loc_1800058E2
0x1800058a7  test    byte ptr [rcx+1Ch], 1
0x1800058ab  jz      short loc_1800058E2
0x1800058ad  mov     edx, 11h
0x1800058b2  jmp     short loc_1800058D2
0x1800058b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058bb  lea     rax, WPP_GLOBAL_Control
0x1800058c2  cmp     rcx, rax
0x1800058c5  jz      short loc_1800058E2
0x1800058c7  test    byte ptr [rcx+1Ch], 1
0x1800058cb  jz      short loc_1800058E2
0x1800058cd  mov     edx, 10h
0x1800058d2  mov     rcx, [rcx+10h]
0x1800058d6  lea     r8, WPP_3fe3f72127b734931da4de68e0accc84_Traceguids
0x1800058dd  call    WPP_SF_
0x1800058e2  xor     eax, eax
0x1800058e4  add     rsp, 28h
0x1800058e8  pop     rdi
0x1800058e9  pop     rsi
0x1800058ea  pop     rbp
0x1800058eb  pop     rbx
0x1800058ec  retn
```
