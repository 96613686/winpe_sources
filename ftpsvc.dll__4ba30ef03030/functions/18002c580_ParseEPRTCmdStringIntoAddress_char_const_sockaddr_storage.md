# ParseEPRTCmdStringIntoAddress(char const *,sockaddr_storage *)

- ea: `0x18002c580`
- end: `0x18002c7a2`
- name: `?ParseEPRTCmdStringIntoAddress@@YAJPEBDPEAUsockaddr_storage@@@Z`
- size: `546`
- prototype: `int(const char *, struct sockaddr_storage *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003add4`

## callees

- `0x18002c580`
- `0x180046ff7`
- `0x180047050`

## import_xrefs

- `WS2_32!getaddrinfo` at `0x18002c6ee`
- `WS2_32!getaddrinfo` at `0x18002c6ee`
- `WS2_32!freeaddrinfo` at `0x18002c74c`
- `WS2_32!freeaddrinfo` at `0x18002c74c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c6f8`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c6f8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002c5c7`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002c5c7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002c760`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002c76b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002c776`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002c760`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002c76b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002c776`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002c5b2`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002c5d3`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002c5b2`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18002c5d3`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002c644`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002c644`

## pseudocode

```c

```
