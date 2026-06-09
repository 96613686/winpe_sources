# GetCmdFromClient

- ea: `0x180008eb8`
- end: `0x180009203`
- name: `GetCmdFromClient`
- size: `843`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003480`
- `0x180007354`

## callees

- `0x180001ce0`
- `0x180002616`
- `0x180002e7c`
- `0x180002ea4`
- `0x180008eb8`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180008f44`
- `KERNEL32!LocalAlloc` at `0x180008f44`
- `KERNEL32!GetLastError` at `0x18000914e`
- `KERNEL32!GetLastError` at `0x1800091b1`
- `KERNEL32!GetLastError` at `0x18000914e`
- `KERNEL32!GetLastError` at `0x1800091b1`
- `KERNEL32!LocalReAlloc` at `0x18000901e`
- `KERNEL32!LocalReAlloc` at `0x18000901e`
- `KERNEL32!LocalFree` at `0x18000911d`
- `KERNEL32!LocalFree` at `0x1800091d6`
- `KERNEL32!LocalFree` at `0x18000911d`
- `KERNEL32!LocalFree` at `0x1800091d6`
- `WS2_32!__imp_recv` at `0x180008fd3`
- `WS2_32!__imp_recv` at `0x180008fd3`
- `WS2_32!__imp_select` at `0x180008fa8`
- `WS2_32!__imp_select` at `0x180008fa8`

## pseudocode

```c
__int64 __fastcall GetCmdFromClient(__int64 a1)
{
  SOCKET v2; // r13
  HLOCAL v3; // rdi
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  int v6; // r12d
  int v7; // ebp
  int v8; // esi
  int v9; // eax
  int v10; // r14d
  int v11; // edx
  int v12; // ebx
  char *v13; // rax
  char *v14; // r8
  __int64 v15; // r9
  char *v16; // rdx
  __int64 v17; // rax
  char *v18; // r10
  char *v19; // rax
  __int64 result; // rax
  __int64 v21; // rbx
  DWORD LastError; // eax
  __int64 v23; // rbx
  DWORD v24; // eax
  timeval timeout; // [rsp+30h] [rbp-478h] BYREF
  fd_set readfds; // [rsp+40h] [rbp-468h] BYREF
  char buf[512]; // [rsp+250h] [rbp-258h] BYREF

  *(&readfds.fd_count + 1) = 0;
  memset_0(&readfds, 0, 0x204u);
  timeout.tv_sec = dwRecvTimeout;
  timeout.tv_usec = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  v2 = *(_QWORD *)(a1 + 8);
  v3 = LocalAlloc(0, 1u);
  if ( v3 )
  {
    v6 = 0;
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      readfds.fd_array[0] = v2;
      readfds.fd_count = 1;
      v9 = select(1, &readfds, 0, 0, &timeout);
      if ( !v9 )
        break;
      if ( v9 == -1 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_51;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          LastError = GetLastError();
          WPP_SF_d(v21, 42, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids, LastError);
          goto LABEL_47;
        }
        goto LABEL_48;
      }
      v10 = recv(v2, buf, 500, 0);
      if ( v10 <= 0 )
      {
        LocalFree(v3);
        return 3;
      }
      v11 = 0;
      while ( 1 )
      {
        v12 = v11 + 1;
        if ( buf[v11] == 10 )
          break;
        ++v11;
        if ( v12 >= v10 )
        {
          v12 = v10;
          goto LABEL_17;
        }
      }
      v6 = 1;
      v7 = v11 + v8 + 1;
LABEL_17:
      v13 = (char *)LocalReAlloc(v3, v12 + v8 + 1LL, 2u);
      v14 = v13;
      if ( !v13 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_51;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v5 = 43;
          goto LABEL_46;
        }
        goto LABEL_48;
      }
      v3 = v13;
      v15 = v12 + 1;
      if ( v12 != -1 )
      {
        v16 = &v13[v8];
        if ( (unsigned __int64)(v12 + 1) <= 0x7FFFFFFF && (v17 = v12, (unsigned __int64)v12 <= 0x7FFFFFFE) )
        {
          v18 = buf;
          do
          {
            if ( !v17 )
              break;
            if ( !*v18 )
              break;
            *v16++ = *v18++;
            --v17;
            --v15;
          }
          while ( v15 );
          v19 = v16 - 1;
          if ( v15 )
            v19 = v16;
          *v19 = 0;
        }
        else
        {
          *v16 = 0;
        }
      }
      v8 += v10;
      if ( v8 > 5000 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_52;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v5 = 44;
          goto LABEL_46;
        }
        goto LABEL_48;
      }
      if ( v6 && v8 >= v7 )
      {
        v14[v7] = 0;
        result = 0;
        *(_QWORD *)(a1 + 32) = v14;
        *(_DWORD *)(a1 + 40) = v7;
        return result;
      }
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_51;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 41;
      goto LABEL_46;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 0xFFFFFFFFLL;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v5 = 40;
LABEL_46:
      WPP_SF_(v4[2], v5, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
LABEL_47:
      v4 = WPP_GLOBAL_Control;
    }
  }
LABEL_48:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
  {
    v23 = v4[2];
    v24 = GetLastError();
    WPP_SF_d(v23, 45, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids, v24);
  }
LABEL_51:
  if ( v3 )
LABEL_52:
    LocalFree(v3);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180008eb8  push    rbx
0x180008eba  push    rbp
0x180008ebb  push    rsi
0x180008ebc  push    rdi
0x180008ebd  push    r12
0x180008ebf  push    r13
0x180008ec1  push    r14
0x180008ec3  push    r15
0x180008ec5  sub     rsp, 468h
0x180008ecc  mov     rax, cs:__security_cookie
0x180008ed3  xor     rax, rsp
0x180008ed6  mov     [rsp+4A8h+var_58], rax
0x180008ede  mov     r15, rcx
0x180008ee1  xor     eax, eax
0x180008ee3  lea     rcx, [rsp+4A8h+readfds]; void *
0x180008ee8  mov     dword ptr [rsp+4A8h+readfds+4], eax
0x180008eec  xor     edx, edx; Val
0x180008eee  mov     r8d, 204h; Size
0x180008ef4  call    memset_0
0x180008ef9  mov     eax, cs:dwRecvTimeout
0x180008eff  mov     [rsp+4A8h+var_478.tv_sec], eax
0x180008f03  mov     [rsp+4A8h+var_478.tv_usec], 0
0x180008f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f12  lea     rax, WPP_GLOBAL_Control
0x180008f19  cmp     rcx, rax
0x180008f1c  jz      short loc_180008F39
0x180008f1e  test    byte ptr [rcx+1Ch], 1
0x180008f22  jz      short loc_180008F39
0x180008f24  mov     rcx, [rcx+10h]
0x180008f28  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180008f2f  mov     edx, 27h ; '''
0x180008f34  call    WPP_SF_
0x180008f39  mov     r13, [r15+8]
0x180008f3d  mov     edx, 1; uBytes
0x180008f42  xor     ecx, ecx; uFlags
0x180008f44  call    cs:__imp_LocalAlloc
0x180008f4a  mov     rdi, rax
0x180008f4d  test    rax, rax
0x180008f50  jnz     short loc_180008F7B
0x180008f52  mov     rbx, cs:WPP_GLOBAL_Control
0x180008f59  lea     rsi, WPP_GLOBAL_Control
0x180008f60  cmp     rbx, rsi
0x180008f63  jz      loc_1800091DC
0x180008f69  test    byte ptr [rbx+1Ch], 8
0x180008f6d  jz      loc_1800091A2
0x180008f73  lea     edx, [rax+28h]
0x180008f76  jmp     loc_18000918B
0x180008f7b  xor     r12d, r12d
0x180008f7e  xor     ebp, ebp
0x180008f80  xor     esi, esi
0x180008f82  xor     r9d, r9d; exceptfds
0x180008f85  mov     [rsp+4A8h+readfds.fd_array], r13
0x180008f8a  lea     rax, [rsp+4A8h+var_478]
0x180008f8f  mov     [rsp+4A8h+readfds.fd_count], 1
0x180008f97  xor     r8d, r8d; writefds
0x180008f9a  mov     [rsp+4A8h+timeout], rax; timeout
0x180008f9f  lea     rdx, [rsp+4A8h+readfds]; readfds
0x180008fa4  lea     ecx, [r9+1]; nfds
0x180008fa8  call    cs:__imp_select
0x180008fae  test    eax, eax
0x180008fb0  jz      loc_18000916D
0x180008fb6  cmp     eax, 0FFFFFFFFh
0x180008fb9  jz      loc_18000912D
0x180008fbf  xor     r9d, r9d; flags
0x180008fc2  lea     rdx, [rsp+4A8h+buf]; buf
0x180008fca  mov     r8d, 1F4h; len
0x180008fd0  mov     rcx, r13; s
0x180008fd3  call    cs:__imp_recv
0x180008fd9  mov     r14d, eax
0x180008fdc  test    eax, eax
0x180008fde  jle     loc_180009115
0x180008fe4  xor     edx, edx
0x180008fe6  mov     ecx, edx
0x180008fe8  lea     ebx, [rdx+1]
0x180008feb  cmp     [rsp+rcx+4A8h+buf], 0Ah
0x180008ff3  jz      short loc_180009001
0x180008ff5  mov     edx, ebx
0x180008ff7  cmp     ebx, r14d
0x180008ffa  jl      short loc_180008FE6
0x180008ffc  mov     ebx, r14d
0x180008fff  jmp     short loc_18000900C
0x180009001  lea     ebp, [rsi+1]
0x180009004  mov     r12d, 1
0x18000900a  add     ebp, edx
0x18000900c  lea     eax, [rbx+rsi]
0x18000900f  mov     r8d, 2; uFlags
0x180009015  movsxd  rdx, eax
0x180009018  mov     rcx, rdi; hMem
0x18000901b  inc     rdx; uBytes
0x18000901e  call    cs:__imp_LocalReAlloc
0x180009024  mov     r8, rax
0x180009027  test    rax, rax
0x18000902a  jz      loc_1800090ED
0x180009030  lea     ecx, [rbx+1]
0x180009033  mov     rdi, rax
0x180009036  movsxd  r9, ecx
0x180009039  test    ecx, ecx
0x18000903b  jz      short loc_18000908F
0x18000903d  movsxd  rdx, esi
0x180009040  add     rdx, rax
0x180009043  cmp     r9, 7FFFFFFFh
0x18000904a  ja      short loc_180009057
0x18000904c  movsxd  rax, ebx
0x18000904f  cmp     rax, 7FFFFFFEh
0x180009055  jbe     short loc_18000905C
0x180009057  mov     byte ptr [rdx], 0
0x18000905a  jmp     short loc_18000908F
0x18000905c  lea     r10, [rsp+4A8h+buf]
0x180009064  test    rax, rax
0x180009067  jz      short loc_180009081
0x180009069  mov     cl, [r10]
0x18000906c  test    cl, cl
0x18000906e  jz      short loc_180009081
0x180009070  mov     [rdx], cl
0x180009072  inc     r10
0x180009075  inc     rdx
0x180009078  dec     rax
0x18000907b  sub     r9, 1
0x18000907f  jnz     short loc_180009064
0x180009081  test    r9, r9
0x180009084  lea     rax, [rdx-1]
0x180009088  cmovnz  rax, rdx
0x18000908c  mov     byte ptr [rax], 0
0x18000908f  add     esi, r14d
0x180009092  cmp     esi, 1388h
0x180009098  jg      short loc_1800090C2
0x18000909a  test    r12d, r12d
0x18000909d  jz      loc_180008F82
0x1800090a3  cmp     esi, ebp
0x1800090a5  jl      loc_180008F82
0x1800090ab  movsxd  rax, ebp
0x1800090ae  mov     byte ptr [rax+r8], 0
0x1800090b3  xor     eax, eax
0x1800090b5  mov     [r15+20h], r8
0x1800090b9  mov     [r15+28h], ebp
0x1800090bd  jmp     loc_1800091DF
0x1800090c2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800090c9  lea     rsi, WPP_GLOBAL_Control
0x1800090d0  cmp     rbx, rsi
0x1800090d3  jz      loc_1800091D3
0x1800090d9  test    byte ptr [rbx+1Ch], 8
0x1800090dd  jz      loc_1800091A2
0x1800090e3  mov     edx, 2Ch ; ','
0x1800090e8  jmp     loc_18000918B
0x1800090ed  mov     rbx, cs:WPP_GLOBAL_Control
0x1800090f4  lea     rsi, WPP_GLOBAL_Control
0x1800090fb  cmp     rbx, rsi
0x1800090fe  jz      loc_1800091CE
0x180009104  test    byte ptr [rbx+1Ch], 8
0x180009108  jz      loc_1800091A2
0x18000910e  mov     edx, 2Bh ; '+'
0x180009113  jmp     short loc_18000918B
0x180009115  test    rdi, rdi
0x180009118  jz      short loc_180009123
0x18000911a  mov     rcx, rdi; hMem
0x18000911d  call    cs:__imp_LocalFree
0x180009123  mov     eax, 3
0x180009128  jmp     loc_1800091DF
0x18000912d  mov     rbx, cs:WPP_GLOBAL_Control
0x180009134  lea     rsi, WPP_GLOBAL_Control
0x18000913b  cmp     rbx, rsi
0x18000913e  jz      loc_1800091CE
0x180009144  test    byte ptr [rbx+1Ch], 2
0x180009148  jz      short loc_1800091A2
0x18000914a  mov     rbx, [rbx+10h]
0x18000914e  call    cs:__imp_GetLastError
0x180009154  mov     edx, 2Ah ; '*'
0x180009159  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009160  mov     r9d, eax
0x180009163  mov     rcx, rbx
0x180009166  call    WPP_SF_d
0x18000916b  jmp     short loc_18000919B
0x18000916d  mov     rbx, cs:WPP_GLOBAL_Control
0x180009174  lea     rsi, WPP_GLOBAL_Control
0x18000917b  cmp     rbx, rsi
0x18000917e  jz      short loc_1800091CE
0x180009180  test    byte ptr [rbx+1Ch], 2
0x180009184  jz      short loc_1800091A2
0x180009186  mov     edx, 29h ; ')'
0x18000918b  mov     rcx, [rbx+10h]
0x18000918f  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009196  call    WPP_SF_
0x18000919b  mov     rbx, cs:WPP_GLOBAL_Control
0x1800091a2  cmp     rbx, rsi
0x1800091a5  jz      short loc_1800091CE
0x1800091a7  test    byte ptr [rbx+1Ch], 2
0x1800091ab  jz      short loc_1800091CE
0x1800091ad  mov     rbx, [rbx+10h]
0x1800091b1  call    cs:__imp_GetLastError
0x1800091b7  mov     edx, 2Dh ; '-'
0x1800091bc  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800091c3  mov     r9d, eax
0x1800091c6  mov     rcx, rbx
0x1800091c9  call    WPP_SF_d
0x1800091ce  test    rdi, rdi
0x1800091d1  jz      short loc_1800091DC
0x1800091d3  mov     rcx, rdi; hMem
0x1800091d6  call    cs:__imp_LocalFree
0x1800091dc  or      eax, 0FFFFFFFFh
0x1800091df  mov     rcx, [rsp+4A8h+var_58]
0x1800091e7  xor     rcx, rsp; StackCookie
0x1800091ea  call    __security_check_cookie
0x1800091ef  add     rsp, 468h
0x1800091f6  pop     r15
0x1800091f8  pop     r14
0x1800091fa  pop     r13
0x1800091fc  pop     r12
0x1800091fe  pop     rdi
0x1800091ff  pop     rsi
0x180009200  pop     rbp
0x180009201  pop     rbx
0x180009202  retn
```
