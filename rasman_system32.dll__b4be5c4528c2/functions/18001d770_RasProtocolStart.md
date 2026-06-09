# RasProtocolStart

- ea: `0x18001d770`
- end: `0x18001dd62`
- name: `RasProtocolStart`
- size: `1522`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001c40`
- `0x1800030d0`
- `0x1800121b4`
- `0x18001d770`
- `0x1800205f0`
- `0x180021ae4`
- `0x180021b14`
- `0x180021bd0`
- `0x180021edc`
- `0x180021f24`
- `0x180021fd4`
- `0x180022668`
- `0x180025bf8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dbee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001dbee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dbdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dbdd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db43`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001db43`

## pseudocode

```c
__int64 __fastcall RasProtocolStart(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        unsigned int *a11,
        __int64 a12,
        __int64 a13,
        int a14)
{
  __int64 v14; // r12
  PVOID *v17; // rcx
  PVOID *v18; // rcx
  unsigned int v19; // edi
  __int64 v20; // rdx
  HLOCAL v21; // rax
  __int64 v22; // rdx
  void *v23; // rsi
  unsigned int UserSid; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // eax
  DWORD CurrentProcessId; // [rsp+78h] [rbp-50h]

  v14 = a4;
  v17 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qqc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a13, a14 != 0);
    v17 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a11 )
  {
    if ( v17 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
      {
        WPP_SF_(v17[2], 451, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
        {
          WPP_SF_d(v17[2], 452, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, *a11);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
          {
            WPP_SF_q(v17[2], 453, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, *((_QWORD *)a11 + 1));
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
            {
              WPP_SF_q(v17[2], 454, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, *((_QWORD *)a11 + 2));
              v17 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v17 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
              {
                WPP_SF__guid_(v17[2], a2, a3, a11 + 134);
                v17 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v17 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                {
                  WPP_SF_d(v17[2], 456, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a11[138]);
                  v17 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v17 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                  {
                    WPP_SF_d(v17[2], 457, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a11[139]);
                    v17 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v17 != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                    {
                      LOBYTE(a4) = a11[140] != 0;
                      WPP_SF_c(v17[2], 458, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a4);
                      v17 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v17 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                      {
                        LOBYTE(a4) = a11[432] != 0;
                        WPP_SF_c(v17[2], 459, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a4);
                        v17 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v17 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                        {
                          WPP_SF_S(v17[2], 460, a3, a11 + 438);
                          v17 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v17 != &WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
                          {
                            WPP_SF_S(v17[2], 461, a3, (char *)a11 + 2266);
                            v17 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          if ( v17 != &WPP_GLOBAL_Control
                            && (*((_BYTE *)v17 + 28) & 0x40) != 0
                            && *((_BYTE *)v17 + 25) >= 5u )
                          {
                            LOBYTE(a4) = a11[695] != 0;
                            WPP_SF_c(v17[2], 462, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a4);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 && *((_BYTE *)v17 + 25) >= 5u )
  {
    WPP_SF_(v17[2], 463, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    v19 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = 464;
LABEL_92:
      WPP_SF_d(v18[2], v20, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v19);
      return v19;
    }
    return v19;
  }
  if ( !(unsigned int)IsRasmanProcess() || NtCurrentTeb()->IsImpersonating )
  {
    v21 = LocalAlloc(0x40u, 0x1388u);
    v23 = v21;
    if ( v21 )
    {
      UserSid = GetUserSid(v21, v22);
      if ( UserSid )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v26 = 466;
      }
      else
      {
        UserSid = RasSetPortUserData(a1, 8, v23, 5000);
        if ( !UserSid )
          goto LABEL_77;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v26 = 465;
      }
      WPP_SF_d(v25[2], v26, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, UserSid);
LABEL_77:
      LocalFree(v23);
      goto LABEL_78;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 467, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    }
  }
LABEL_78:
  CurrentProcessId = GetCurrentProcessId();
  v27 = SubmitLocalRequest(0x41u, a1, a2, a3, v14, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, CurrentProcessId);
  v19 = v27;
  if ( v27 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v19;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_88;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 468, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v27);
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_88:
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 && *((_BYTE *)v18 + 25) >= 6u )
  {
    v20 = 469;
    goto LABEL_92;
  }
  return v19;
}

```

## disassembly

```asm
0x18001d770  mov     [rsp+arg_8], rdx
0x18001d775  push    rbx
0x18001d776  push    rbp
0x18001d777  push    rsi
0x18001d778  push    rdi
0x18001d779  push    r12
0x18001d77b  push    r13
0x18001d77d  push    r14
0x18001d77f  push    r15
0x18001d781  sub     rsp, 88h
0x18001d788  mov     r12, r9
0x18001d78b  mov     r13, r8
0x18001d78e  mov     rbp, rcx
0x18001d791  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d798  lea     rbx, WPP_GLOBAL_Control
0x18001d79f  mov     r14d, [rsp+0C8h+arg_68]
0x18001d7a7  mov     esi, 40h ; '@'
0x18001d7ac  mov     r15, [rsp+0C8h+arg_60]
0x18001d7b4  cmp     rcx, rbx
0x18001d7b7  jz      short loc_18001D7E7
0x18001d7b9  test    [rcx+1Ch], sil
0x18001d7bd  jz      short loc_18001D7E7
0x18001d7bf  cmp     byte ptr [rcx+19h], 6
0x18001d7c3  jb      short loc_18001D7E7
0x18001d7c5  mov     rcx, [rcx+10h]
0x18001d7c9  test    r14d, r14d
0x18001d7cc  mov     r9, rbp
0x18001d7cf  setnz   al
0x18001d7d2  mov     byte ptr [rsp+0C8h+var_A0], al
0x18001d7d6  mov     [rsp+0C8h+var_A8], r15
0x18001d7db  call    WPP_SF_qqc
0x18001d7e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7e7  mov     rdi, [rsp+0C8h+arg_50]
0x18001d7ef  test    rdi, rdi
0x18001d7f2  jz      loc_18001DAB3
0x18001d7f8  cmp     rcx, rbx
0x18001d7fb  jz      loc_18001DAE1
0x18001d801  mov     bl, 5
0x18001d803  test    [rcx+1Ch], sil
0x18001d807  jz      short loc_18001D82A
0x18001d809  cmp     [rcx+19h], bl
0x18001d80c  jb      short loc_18001D82A
0x18001d80e  mov     rcx, [rcx+10h]
0x18001d812  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d819  mov     edx, 1C3h
0x18001d81e  call    WPP_SF_
0x18001d823  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d82a  lea     rax, WPP_GLOBAL_Control
0x18001d831  cmp     rcx, rax
0x18001d834  jz      loc_18001DADA
0x18001d83a  test    [rcx+1Ch], sil
0x18001d83e  jz      short loc_18001D86B
0x18001d840  cmp     [rcx+19h], bl
0x18001d843  jb      short loc_18001D86B
0x18001d845  mov     r9d, [rdi]
0x18001d848  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d84f  mov     rcx, [rcx+10h]
0x18001d853  mov     edx, 1C4h
0x18001d858  call    WPP_SF_d
0x18001d85d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d864  lea     rax, WPP_GLOBAL_Control
0x18001d86b  cmp     rcx, rax
0x18001d86e  jz      loc_18001DADA
0x18001d874  test    [rcx+1Ch], sil
0x18001d878  jz      short loc_18001D8A6
0x18001d87a  cmp     [rcx+19h], bl
0x18001d87d  jb      short loc_18001D8A6
0x18001d87f  mov     r9, [rdi+8]
0x18001d883  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d88a  mov     rcx, [rcx+10h]
0x18001d88e  mov     edx, 1C5h
0x18001d893  call    WPP_SF_q
0x18001d898  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d89f  lea     rax, WPP_GLOBAL_Control
0x18001d8a6  cmp     rcx, rax
0x18001d8a9  jz      loc_18001DADA
0x18001d8af  test    [rcx+1Ch], sil
0x18001d8b3  jz      short loc_18001D8E1
0x18001d8b5  cmp     [rcx+19h], bl
0x18001d8b8  jb      short loc_18001D8E1
0x18001d8ba  mov     r9, [rdi+10h]
0x18001d8be  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d8c5  mov     rcx, [rcx+10h]
0x18001d8c9  mov     edx, 1C6h
0x18001d8ce  call    WPP_SF_q
0x18001d8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8da  lea     rax, WPP_GLOBAL_Control
0x18001d8e1  cmp     rcx, rax
0x18001d8e4  jz      loc_18001DADA
0x18001d8ea  test    [rcx+1Ch], sil
0x18001d8ee  jz      short loc_18001D913
0x18001d8f0  cmp     [rcx+19h], bl
0x18001d8f3  jb      short loc_18001D913
0x18001d8f5  mov     rcx, [rcx+10h]
0x18001d8f9  lea     r9, [rdi+218h]
0x18001d900  call    WPP_SF__guid_
0x18001d905  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d90c  lea     rax, WPP_GLOBAL_Control
0x18001d913  cmp     rcx, rax
0x18001d916  jz      loc_18001DADA
0x18001d91c  test    [rcx+1Ch], sil
0x18001d920  jz      short loc_18001D951
0x18001d922  cmp     [rcx+19h], bl
0x18001d925  jb      short loc_18001D951
0x18001d927  mov     r9d, [rdi+228h]
0x18001d92e  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d935  mov     rcx, [rcx+10h]
0x18001d939  mov     edx, 1C8h
0x18001d93e  call    WPP_SF_d
0x18001d943  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d94a  lea     rax, WPP_GLOBAL_Control
0x18001d951  cmp     rcx, rax
0x18001d954  jz      loc_18001DADA
0x18001d95a  test    [rcx+1Ch], sil
0x18001d95e  jz      short loc_18001D98F
0x18001d960  cmp     [rcx+19h], bl
0x18001d963  jb      short loc_18001D98F
0x18001d965  mov     r9d, [rdi+22Ch]
0x18001d96c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d973  mov     rcx, [rcx+10h]
0x18001d977  mov     edx, 1C9h
0x18001d97c  call    WPP_SF_d
0x18001d981  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d988  lea     rax, WPP_GLOBAL_Control
0x18001d98f  cmp     rcx, rax
0x18001d992  jz      loc_18001DADA
0x18001d998  test    [rcx+1Ch], sil
0x18001d99c  jz      short loc_18001D9D1
0x18001d99e  cmp     [rcx+19h], bl
0x18001d9a1  jb      short loc_18001D9D1
0x18001d9a3  cmp     dword ptr [rdi+230h], 0
0x18001d9aa  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d9b1  mov     rcx, [rcx+10h]
0x18001d9b5  mov     edx, 1CAh
0x18001d9ba  setnz   r9b
0x18001d9be  call    WPP_SF_c
0x18001d9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9ca  lea     rax, WPP_GLOBAL_Control
0x18001d9d1  cmp     rcx, rax
0x18001d9d4  jz      loc_18001DADA
0x18001d9da  test    [rcx+1Ch], sil
0x18001d9de  jz      short loc_18001DA13
0x18001d9e0  cmp     [rcx+19h], bl
0x18001d9e3  jb      short loc_18001DA13
0x18001d9e5  cmp     dword ptr [rdi+6C0h], 0
0x18001d9ec  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001d9f3  mov     rcx, [rcx+10h]
0x18001d9f7  mov     edx, 1CBh
0x18001d9fc  setnz   r9b
0x18001da00  call    WPP_SF_c
0x18001da05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da0c  lea     rax, WPP_GLOBAL_Control
0x18001da13  cmp     rcx, rax
0x18001da16  jz      loc_18001DADA
0x18001da1c  test    [rcx+1Ch], sil
0x18001da20  jz      short loc_18001DA4A
0x18001da22  cmp     [rcx+19h], bl
0x18001da25  jb      short loc_18001DA4A
0x18001da27  mov     rcx, [rcx+10h]
0x18001da2b  lea     r9, [rdi+6D8h]
0x18001da32  mov     edx, 1CCh
0x18001da37  call    WPP_SF_S
0x18001da3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da43  lea     rax, WPP_GLOBAL_Control
0x18001da4a  cmp     rcx, rax
0x18001da4d  jz      loc_18001DADA
0x18001da53  test    [rcx+1Ch], sil
0x18001da57  jz      short loc_18001DA81
0x18001da59  cmp     [rcx+19h], bl
0x18001da5c  jb      short loc_18001DA81
0x18001da5e  mov     rcx, [rcx+10h]
0x18001da62  lea     r9, [rdi+8DAh]
0x18001da69  mov     edx, 1CDh
0x18001da6e  call    WPP_SF_S
0x18001da73  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da7a  lea     rax, WPP_GLOBAL_Control
0x18001da81  cmp     rcx, rax
0x18001da84  jz      short loc_18001DADA
0x18001da86  test    [rcx+1Ch], sil
0x18001da8a  jz      short loc_18001DADA
0x18001da8c  cmp     [rcx+19h], bl
0x18001da8f  jb      short loc_18001DADA
0x18001da91  cmp     dword ptr [rdi+0ADCh], 0
0x18001da98  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001da9f  mov     rcx, [rcx+10h]
0x18001daa3  mov     edx, 1CEh
0x18001daa8  setnz   r9b
0x18001daac  call    WPP_SF_c
0x18001dab1  jmp     short loc_18001DADA
0x18001dab3  cmp     rcx, rbx
0x18001dab6  jz      short loc_18001DAE1
0x18001dab8  test    [rcx+1Ch], sil
0x18001dabc  jz      short loc_18001DAE1
0x18001dabe  mov     bl, 5
0x18001dac0  cmp     [rcx+19h], bl
0x18001dac3  jb      short loc_18001DADA
0x18001dac5  mov     rcx, [rcx+10h]
0x18001dac9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dad0  mov     edx, 1CFh
0x18001dad5  call    WPP_SF_
0x18001dada  lea     rbx, WPP_GLOBAL_Control
0x18001dae1  mov     rcx, rbp
0x18001dae4  call    ValidatePortHandle
0x18001dae9  test    eax, eax
0x18001daeb  jnz     short loc_18001DB21
0x18001daed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daf4  mov     edi, 259h
0x18001daf9  cmp     rcx, rbx
0x18001dafc  jz      loc_18001DD4B
0x18001db02  test    [rcx+1Ch], sil
0x18001db06  jz      loc_18001DD4B
0x18001db0c  mov     bl, 2
0x18001db0e  cmp     [rcx+19h], bl
0x18001db11  jb      loc_18001DD4B
0x18001db17  mov     edx, 1D0h
0x18001db1c  jmp     loc_18001DD38
0x18001db21  call    IsRasmanProcess
0x18001db26  mov     bl, 2
0x18001db28  test    eax, eax
0x18001db2a  jz      short loc_18001DB3C
0x18001db2c  mov     eax, gs:179Ch
0x18001db34  test    eax, eax
0x18001db36  jz      loc_18001DBEE
0x18001db3c  mov     edx, 1388h; uBytes
0x18001db41  mov     ecx, esi; uFlags
0x18001db43  call    cs:__imp_LocalAlloc
0x18001db4a  nop     dword ptr [rax+rax+00h]
0x18001db4f  mov     rsi, rax
0x18001db52  test    rax, rax
0x18001db55  jz      loc_18001DCCB
0x18001db5b  mov     rcx, rax
0x18001db5e  call    GetUserSid
0x18001db63  test    eax, eax
0x18001db65  jnz     short loc_18001DBA4
0x18001db67  mov     r9d, 1388h
0x18001db6d  lea     edx, [rax+8]
0x18001db70  mov     r8, rsi
0x18001db73  mov     rcx, rbp
0x18001db76  call    RasSetPortUserData
0x18001db7b  test    eax, eax
0x18001db7d  jz      short loc_18001DBDA
0x18001db7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db86  lea     rdx, WPP_GLOBAL_Control
0x18001db8d  cmp     rcx, rdx
0x18001db90  jz      short loc_18001DBDA
0x18001db92  test    byte ptr [rcx+1Ch], 40h
0x18001db96  jz      short loc_18001DBDA
0x18001db98  cmp     [rcx+19h], bl
0x18001db9b  jb      short loc_18001DBDA
0x18001db9d  mov     edx, 1D1h
0x18001dba2  jmp     short loc_18001DBC7
0x18001dba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbab  lea     rdx, WPP_GLOBAL_Control
0x18001dbb2  cmp     rcx, rdx
0x18001dbb5  jz      short loc_18001DBDA
0x18001dbb7  test    byte ptr [rcx+1Ch], 40h
0x18001dbbb  jz      short loc_18001DBDA
0x18001dbbd  cmp     [rcx+19h], bl
0x18001dbc0  jb      short loc_18001DBDA
0x18001dbc2  mov     edx, 1D2h
0x18001dbc7  mov     rcx, [rcx+10h]
0x18001dbcb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001dbd2  mov     r9d, eax
0x18001dbd5  call    WPP_SF_d
0x18001dbda  mov     rcx, rsi; hMem
0x18001dbdd  call    cs:__imp_LocalFree
0x18001dbe4  nop     dword ptr [rax+rax+00h]
0x18001dbe9  mov     esi, 40h ; '@'
0x18001dbee  call    cs:__imp_GetCurrentProcessId
0x18001dbf5  nop     dword ptr [rax+rax+00h]
0x18001dbfa  mov     r8, [rsp+0C8h+arg_8]
0x18001dc02  mov     ecx, 41h ; 'A'
0x18001dc07  mov     [rsp+0C8h+var_50], eax
0x18001dc0b  mov     r9, r13
0x18001dc0e  mov     rax, [rsp+0C8h+arg_58]
0x18001dc16  mov     rdx, rbp
0x18001dc19  mov     [rsp+0C8h+var_58], r14d
0x18001dc1e  mov     [rsp+0C8h+var_60], r15
0x18001dc23  mov     [rsp+0C8h+var_68], rax
0x18001dc28  mov     rax, [rsp+0C8h+arg_48]
0x18001dc30  mov     [rsp+0C8h+var_70], rdi
0x18001dc35  mov     [rsp+0C8h+var_78], rax
0x18001dc3a  mov     rax, [rsp+0C8h+arg_40]
0x18001dc42  mov     [rsp+0C8h+var_80], rax
0x18001dc47  mov     rax, [rsp+0C8h+arg_38]
0x18001dc4f  mov     [rsp+0C8h+var_88], rax
0x18001dc54  mov     rax, [rsp+0C8h+arg_30]
0x18001dc5c  mov     [rsp+0C8h+var_90], rax
0x18001dc61  mov     rax, [rsp+0C8h+arg_28]
0x18001dc69  mov     [rsp+0C8h+var_98], rax
0x18001dc6e  mov     rax, [rsp+0C8h+arg_20]
0x18001dc76  mov     [rsp+0C8h+var_A0], rax
0x18001dc7b  mov     [rsp+0C8h+var_A8], r12
0x18001dc80  call    SubmitLocalRequest
0x18001dc85  mov     edi, eax
0x18001dc87  test    eax, eax
0x18001dc89  jz      loc_18001DD14
0x18001dc8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc96  lea     rbp, WPP_GLOBAL_Control
0x18001dc9d  cmp     rcx, rbp
  ... truncated ...
```
