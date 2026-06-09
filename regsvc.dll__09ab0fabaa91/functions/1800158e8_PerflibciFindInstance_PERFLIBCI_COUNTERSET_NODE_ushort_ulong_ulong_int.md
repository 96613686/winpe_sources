# PerflibciFindInstance(PERFLIBCI_COUNTERSET_NODE *,ushort *,ulong,ulong,int)

- ea: `0x1800158e8`
- end: `0x180015b15`
- name: `?PerflibciFindInstance@@YAPEAUPERFLIBCI_INSTANCE_NODE@@PEAUPERFLIBCI_COUNTERSET_NODE@@PEAGKKH@Z`
- size: `557`
- prototype: `struct PERFLIBCI_INSTANCE_NODE *__fastcall(struct _RTL_CRITICAL_SECTION *, unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002810`

## callees

- `0x180005da0`
- `0x1800071b0`
- `0x18000fea0`
- `0x1800158e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ae2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015ae2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001592a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001592a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015afb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015afb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015978`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015978`

## pseudocode

```c
struct PERFLIBCI_INSTANCE_NODE *__fastcall PerflibciFindInstance(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        int a4)
{
  _QWORD *v5; // rbx
  DWORD v6; // edi
  int v7; // r14d
  struct PERFLIBCI_RED_BLACK_NODE *v8; // rbx
  struct PERFLIBCI_RED_BLACK_NODE **v9; // r12
  int v10; // r15d
  __int64 v11; // rbp
  __int64 v12; // rsi
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rcx
  char *v16; // rax
  struct PERFLIBCI_RED_BLACK_NODE *v17; // r11
  struct PERFLIBCI_RED_BLACK_NODE **p_LockCount; // rsi
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+30h] [rbp-58h]

  if ( !a1 )
  {
    v5 = 0;
    v6 = 13;
    goto LABEL_37;
  }
  v7 = 0;
  lpCriticalSection = a1 + 1;
  EnterCriticalSection(a1 + 1);
  v8 = *(struct PERFLIBCI_RED_BLACK_NODE **)&a1->LockCount;
  v9 = 0;
  v10 = 0;
  v11 = -1;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v8 )
      {
        if ( !v7 )
        {
          v14 = -1;
          do
            ++v14;
          while ( a2[v14] );
          if ( !((unsigned __int64)(2 * v14 + 2) >> 32) )
          {
            v15 = ((2 * (_DWORD)v14 + 9) & 0xFFFFFFF8) + 72LL;
            if ( !HIDWORD(v15) )
            {
              v16 = (char *)operator new((unsigned int)v15);
              if ( v16 )
              {
                v5 = v16 + 48;
                *((_QWORD *)v16 + 4) = v16 + 48;
                *((_QWORD *)v16 + 3) = a1->DebugInfo;
                a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v16;
                *((_QWORD *)v16 + 2) = v9;
                *((_DWORD *)v16 + 10) = 1;
                *((_DWORD *)v16 + 16) = a4;
                *((_DWORD *)v16 + 14) = a3;
                *((_DWORD *)v16 + 15) = 1;
                *((_QWORD *)v16 + 6) = v16 + 72;
                do
                  ++v11;
                while ( a2[v11] );
                StringCchCopyW((unsigned __int16 *)v16 + 36, v11 + 1, a2);
                if ( v9 )
                {
                  p_LockCount = (struct PERFLIBCI_RED_BLACK_NODE **)&a1->LockCount;
                  if ( v10 >= 0 )
                    v9[1] = v17;
                  else
                    *v9 = v17;
                }
                else
                {
                  p_LockCount = (struct PERFLIBCI_RED_BLACK_NODE **)&a1->LockCount;
                  *(_QWORD *)&a1->LockCount = v17;
                }
                PerflibciInsertRedBlackNode(p_LockCount, v17);
                *((_DWORD *)*p_LockCount + 10) = 0;
                goto LABEL_34;
              }
            }
          }
          v7 = 14;
        }
        v5 = 0;
        goto LABEL_34;
      }
      v12 = *((_QWORD *)v8 + 4);
      if ( v12 )
        break;
      v8 = 0;
      v7 = 13;
    }
    v13 = CompareStringOrdinal(a2, -1, *(LPCWCH *)v12, -1, 1);
    v10 = v13 - 2;
    if ( v13 == 2 )
      break;
LABEL_11:
    v9 = (struct PERFLIBCI_RED_BLACK_NODE **)v8;
    if ( v10 >= 0 )
      v8 = (struct PERFLIBCI_RED_BLACK_NODE *)((char *)v8 + 8);
    v8 = *(struct PERFLIBCI_RED_BLACK_NODE **)v8;
  }
  if ( a3 < *(_DWORD *)(v12 + 8) )
  {
    v10 = -1;
    goto LABEL_11;
  }
  if ( a3 > *(_DWORD *)(v12 + 8) )
  {
    v10 = 1;
    goto LABEL_11;
  }
  if ( !*(_DWORD *)(v12 + 16) )
    *(_DWORD *)(v12 + 16) = a4;
  v5 = (_QWORD *)((char *)v8 + 48);
  ++*((_DWORD *)v5 + 3);
LABEL_34:
  LeaveCriticalSection(lpCriticalSection);
  if ( !v5 )
  {
    v6 = v7;
    if ( !v7 )
      v6 = 87;
LABEL_37:
    SetLastError(v6);
  }
  return (struct PERFLIBCI_INSTANCE_NODE *)v5;
}

```

## disassembly

```asm
0x1800158e8  mov     [rsp+arg_18], r9d
0x1800158ed  mov     [rsp+arg_10], r8d
0x1800158f2  mov     [rsp+lpString1], rdx
0x1800158f7  push    rbx
0x1800158f8  push    rbp
0x1800158f9  push    rsi
0x1800158fa  push    rdi
0x1800158fb  push    r12
0x1800158fd  push    r13
0x1800158ff  push    r14
0x180015901  push    r15
0x180015903  sub     rsp, 48h
0x180015907  xor     ebp, ebp
0x180015909  mov     r13, rcx
0x18001590c  test    rcx, rcx
0x18001590f  jnz     short loc_18001591B
0x180015911  mov     ebx, ebp
0x180015913  lea     edi, [rcx+0Dh]
0x180015916  jmp     loc_180015AF9
0x18001591b  lea     rax, [rcx+28h]
0x18001591f  mov     r14d, ebp
0x180015922  mov     rcx, rax; lpCriticalSection
0x180015925  mov     [rsp+88h+lpCriticalSection], rax
0x18001592a  call    cs:__imp_EnterCriticalSection
0x180015930  xor     edx, edx
0x180015932  lea     rsi, [r13+8]
0x180015936  mov     rbx, [rsi]
0x180015939  mov     r12d, edx
0x18001593c  mov     [rsp+88h+arg_0], rsi
0x180015944  mov     r15d, edx
0x180015947  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001594b  lea     edi, [rdx+0Dh]
0x18001594e  test    rbx, rbx
0x180015951  jz      loc_1800159D8
0x180015957  mov     rsi, [rbx+20h]
0x18001595b  test    rsi, rsi
0x18001595e  jz      short loc_1800159B5
0x180015960  mov     r8, [rsi]; lpString2
0x180015963  mov     r9d, ebp; cchCount2
0x180015966  mov     rcx, [rsp+88h+lpString1]; lpString1
0x18001596e  mov     edx, ebp; cchCount1
0x180015970  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180015978  call    cs:__imp_CompareStringOrdinal
0x18001597e  xor     edx, edx
0x180015980  lea     r15d, [rax-2]
0x180015984  test    r15d, r15d
0x180015987  jnz     short loc_1800159A2
0x180015989  mov     eax, [rsp+88h+arg_10]
0x180015990  cmp     eax, [rsi+8]
0x180015993  jnb     short loc_18001599A
0x180015995  mov     r15d, ebp
0x180015998  jmp     short loc_1800159A2
0x18001599a  jbe     short loc_1800159BD
0x18001599c  mov     r15d, 1
0x1800159a2  lea     rax, [rbx+8]
0x1800159a6  mov     r12, rbx
0x1800159a9  test    r15d, r15d
0x1800159ac  cmovns  rbx, rax
0x1800159b0  mov     rbx, [rbx]
0x1800159b3  jmp     short loc_18001594E
0x1800159b5  mov     rbx, rdx
0x1800159b8  mov     r14d, edi
0x1800159bb  jmp     short loc_18001594E
0x1800159bd  cmp     [rsi+10h], edx
0x1800159c0  jnz     short loc_1800159CC
0x1800159c2  mov     eax, [rsp+88h+arg_18]
0x1800159c9  mov     [rsi+10h], eax
0x1800159cc  add     rbx, 30h ; '0'
0x1800159d0  inc     dword ptr [rbx+0Ch]
0x1800159d3  jmp     loc_180015ADB
0x1800159d8  test    r14d, r14d
0x1800159db  jnz     loc_180015AD8
0x1800159e1  mov     rdi, [rsp+88h+lpString1]
0x1800159e9  mov     rax, rbp
0x1800159ec  inc     rax
0x1800159ef  cmp     [rdi+rax*2], dx
0x1800159f3  jnz     short loc_1800159EC
0x1800159f5  lea     rcx, ds:2[rax*2]
0x1800159fd  mov     rax, rcx
0x180015a00  shr     rax, 20h
0x180015a04  test    eax, eax
0x180015a06  jnz     loc_180015AD2
0x180015a0c  lea     eax, [rcx+7]
0x180015a0f  mov     ecx, 0FFFFFFF8h
0x180015a14  and     rcx, rax
0x180015a17  add     rcx, 48h ; 'H'
0x180015a1b  mov     rax, rcx
0x180015a1e  shr     rax, 20h
0x180015a22  test    eax, eax
0x180015a24  jnz     loc_180015AD2
0x180015a2a  mov     ecx, ecx
0x180015a2c  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180015a31  xor     edx, edx
0x180015a33  mov     r11, rax
0x180015a36  test    rax, rax
0x180015a39  jz      loc_180015AD2
0x180015a3f  mov     r8d, [rsp+88h+arg_10]
0x180015a47  lea     rbx, [rax+30h]
0x180015a4b  mov     [rax+20h], rbx
0x180015a4f  mov     rcx, [r13+0]
0x180015a53  mov     [rax+18h], rcx
0x180015a57  lea     rcx, [rbx+18h]; unsigned __int16 *
0x180015a5b  mov     [r13+0], rax
0x180015a5f  mov     [rax+10h], r12
0x180015a63  mov     dword ptr [rax+28h], 1
0x180015a6a  mov     eax, [rsp+88h+arg_18]
0x180015a71  mov     [rbx+10h], eax
0x180015a74  mov     [rbx+8], r8d
0x180015a78  mov     dword ptr [rbx+0Ch], 1
0x180015a7f  mov     [rbx], rcx
0x180015a82  inc     rbp
0x180015a85  cmp     [rdi+rbp*2], dx
0x180015a89  jnz     short loc_180015A82
0x180015a8b  lea     rdx, [rbp+1]; unsigned __int64
0x180015a8f  mov     r8, rdi; unsigned __int16 *
0x180015a92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015a97  xor     ebp, ebp
0x180015a99  test    r12, r12
0x180015a9c  jz      short loc_180015AB8
0x180015a9e  mov     rsi, [rsp+88h+arg_0]
0x180015aa6  test    r15d, r15d
0x180015aa9  jns     short loc_180015AB1
0x180015aab  mov     [r12], r11
0x180015aaf  jmp     short loc_180015ABF
0x180015ab1  mov     [r12+8], r11
0x180015ab6  jmp     short loc_180015ABF
0x180015ab8  lea     rsi, [r13+8]
0x180015abc  mov     [rsi], r11
0x180015abf  mov     rdx, r11; struct PERFLIBCI_RED_BLACK_NODE *
0x180015ac2  mov     rcx, rsi; struct PERFLIBCI_RED_BLACK_NODE **
0x180015ac5  call    ?PerflibciInsertRedBlackNode@@YAXPEAPEAUPERFLIBCI_RED_BLACK_NODE@@PEAU1@@Z; PerflibciInsertRedBlackNode(PERFLIBCI_RED_BLACK_NODE * *,PERFLIBCI_RED_BLACK_NODE *)
0x180015aca  mov     rax, [rsi]
0x180015acd  mov     [rax+28h], ebp
0x180015ad0  jmp     short loc_180015ADD
0x180015ad2  mov     r14d, 0Eh
0x180015ad8  mov     rbx, rdx
0x180015adb  xor     ebp, ebp
0x180015add  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180015ae2  call    cs:__imp_LeaveCriticalSection
0x180015ae8  test    rbx, rbx
0x180015aeb  jnz     short loc_180015B01
0x180015aed  test    r14d, r14d
0x180015af0  lea     eax, [rbx+57h]
0x180015af3  mov     edi, r14d
0x180015af6  cmovz   edi, eax
0x180015af9  mov     ecx, edi; dwErrCode
0x180015afb  call    cs:__imp_SetLastError
0x180015b01  mov     rax, rbx
0x180015b04  add     rsp, 48h
0x180015b08  pop     r15
0x180015b0a  pop     r14
0x180015b0c  pop     r13
0x180015b0e  pop     r12
0x180015b10  pop     rdi
0x180015b11  pop     rsi
0x180015b12  pop     rbp
0x180015b13  pop     rbx
0x180015b14  retn
```
